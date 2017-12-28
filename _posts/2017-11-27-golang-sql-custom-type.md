---
title:  "Custom type for database/sql"
last_modified_at: 2017-11-27
categories: 
  - Program
  - Golang
tags:
  - go
toc: false
toc_label: ""
---

Data structure serialization in databases can be difficult with golang types.

For example, we want to have a custom type as an attribute in a type. How can we get this typed attribute inserted and read from a sql database? Golang offers a mechanism to allow for this: Implement `Scanner` and `Valuer` database/sql interfaces.

Imagine we have the simplest representation of `Post`: 
```go
type PostTime time.Time

type Post struct {
	Content  string   `json:"content"`
	CreateAt PostTime `json:"create_at"`
}
```

```go
// for database/sql
func (pt PostTime) Value() (driver.Value, error) {
	if pt.IsZero() {
		return time.Now(), nil
	}

	return pt.Time, nil
}

// database/sql Scanner
func (pt *PostTime) Scan(value interface{}) error {
	if value == nil {
		return nil
	}

	if t, ok := value.(time.Time); ok {
		*pt = t
		return nil
	}

	// otherwise, return an error
	return errors.New("failed to scan PostTime")
}
```


```go
var (
	TimeLayout = "2006-01-02T15:04:05"
)

func (pt *PostTime) UnmarshalJSON(b []byte) (err error) {
	if b == nil || len(b) == 0 {
		*pt = time.Now()
		return
	}

	s := string(b)
	// time in seconds
	if seconds, err := strconv.ParseInt(s, 10, 64); err == nil {
		*pt = time.Unix(seconds, 0)
		return nil
	}

	s = s[1 : len(s)-1]
	t, err := time.Parse(time.RFC3339Nano, s)
	if err != nil {
		t, err = time.Parse(TimeLayout, s)
	}

	*pt = t
	return nil
}

func (pt PostTime) MarshalJSON() ([]byte, error) {
    // note: need add the double quotes if the output is string
	str := fmt.Sprintf("\"%s\"", pt.Format(TimeLayout)) 
	return []byte(str), nil
}
```

[golang playground](https://play.golang.org/p/6ohSjWv5kI)

