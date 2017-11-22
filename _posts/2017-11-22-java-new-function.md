---
title:  "What is the 'new' keyword in Javascript?"
last_modified_at: 2017-11-22
categories: 
  - Program
  - Javascript
tags:
  - javascript
toc: false
toc_label: ""
---

What's the difference for the following function?

```javascript
function test1() {
   this.value = "attr";
   return 1
}

var t1 = new test1();
console.log(t1.value); //attr
```

```javascript
function test2() {
   this.value = "attr";
   return {}
}

var t2 = new test2();
console.log(t2.value); // undefined
```

### Why is there a difference between the values?

According to the answer from stackoverflow [What is the 'new' keyword in Javascript?](https://stackoverflow.com/questions/1646698/what-is-the-new-keyword-in-javascript)

**The 'new' keyword does 5 things:**
1. It creates a new object. The type of this object, is simply object.
2. It sets this new object's internal, inaccessible, [[prototype]] (i.e. __proto__) property to be the constructor function's external, accessible, prototype object (every function object automatically has a prototype property).
3. It makes the this variable point to the newly created object.
4. It executes the constructor function, using the newly created object whenever this is mentioned.
5. It returns the newly created object, unless the constructor function returns a *non-null* object reference. In this case, that object reference is returned instead.

**Becuase the second function return a new empty object, then the 'new' keyword will return the empty object instead of function object.**

