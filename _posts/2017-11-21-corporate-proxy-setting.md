---
title:  "Proxy Settings"
last_modified_at: 2017-11-21
categories: 
  - Program
  - Tool
tags:
  - proxy
toc: true
toc_label: "Proxy setup"
---

# Configuring a corporate proxy

You probably will need to configure all tools to bypass the corporate proxy in most company. First you can try to configure the `HTTP_PROXY` and `HTTPS_PROXY` environment variables or use a tool like Cntlm. But sometime this probably won’t be enough, so you will need to configure separately all the tools.

## Introduction
Supposing your proxy is defined with:
```
username
password
host
port
```
The resulting configuration is: `http://username:password@host:port`

## Use tool Cntlm
### Install [Cntlm](http://cntlm.sourceforge.net/)
Cntlm (user-friendly wiki / technical manual) is an NTLM / NTLM Session Response / NTLMv2 authenticating HTTP proxy intended to help you break free from the chains of Microsoft proprietary world. You can use a free OS and honor our noble idea, but you can't hide. Once you're behind those cold steel bars of a corporate proxy server requiring NTLM authentication, you're done with. The same even applies to 3rd party Windows applications, which don't support NTLM natively.

#### 1) Window
Download window version [cntlm-0.92.3-win32.zip or cntlm-0.92.3-setup.exe](https://sourceforge.net/projects/cntlm/files/cntlm/cntlm%200.92.3/)

*NOTE: If you do't have the admin permission, download the portable version **cntlm-0.92.3-win32.zip***

#### 2) Linux
Download [cntlm-0.92.3.tar.gz](https://nchc.dl.sourceforge.net/project/cntlm/cntlm/cntlm%200.92.3/cntlm-0.92.3.zip)

```bash
./configure
make
sudo make install
```

#### 3) Mac OS
```
$ brew install cntlm
==> Downloading https://homebrew.bintray.com/bottles/cntlm-0.92.3.high_sierra.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring cntlm-0.92.3.high_sierra.bottle.1.tar.gz
==> Caveats
Edit /usr/local/etc/cntlm.conf to configure Cntlm

To have launchd start cntlm now and restart at startup:
  sudo brew services start cntlm
==> Summary
🍺  /usr/local/Cellar/cntlm/0.92.3: 9 files, 144.6KB
```

### Edit the configuration cntlm.conf
```
Domain      companyDomain
Username    yourid
Password    password

Proxy       host:port #company proxy server and port
```

## Proxy setup separately
If you don't use any tool like cntlm, you need to configure each tool individually.

### Yarn configuration
Use these commands:
```
yarn config set proxy http://username:password@host:port
yarn config set https-proxy http://username:password@host:port
```

### NPM configuration
1. Use these commands:
```
npm config set proxy http://username:password@host:port
npm config set https-proxy http://username:password@host:port
```
2. Or you can edit directly your ~/.npmrc file:
```
proxy=http://username:password@host:port
https-proxy=http://username:password@host:port
https_proxy=http://username:password@host:port
```

### Git configuration
1. Use these commands:
```shell
git config --global http.proxy http://username:password@host:port
git config --global https.proxy http://username:password@host:port
```
2. Or you can edit directly your ~/.gitconfig file:
```
[http]
      proxy = http://username:password@host:port
[https]
      proxy = http://username:password@host:port
```

### Bower configuration
Edit your ~/.bowerrc file:
```
{
    "proxy":"http://username:password@host:port",
    "https-proxy":"http://username:password@host:port"
}
```

### Maven configuration
Edit the proxies session in your ~/.m2/settings.xml file

### Maven Wrapper
Create a new file .mvn/jvm.config inside the project folder and set the properties accordingly:
```
-Dhttp.proxyHost=host 
-Dhttp.proxyPort=port 
-Dhttps.proxyHost=host 
-Dhttps.proxyPort=port 
-Dhttp.proxyUser=username 
-Dhttp.proxyPassword=password
```

### Gradle configuration
Add the below in your gradle.properties file and in your gradle/wrapper/gradle-wrapper.properties file if you are downloading the wrapper over a proxy. 
If you want to set these properties globally then add it in USER_HOME/.gradle/gradle.properties file
```
systemProp.proxySet="true"

systemProp.http.keepAlive="true"
systemProp.http.proxyHost=host
systemProp.http.proxyPort=port
systemProp.http.proxyUser=username
systemProp.http.proxyPassword=password
systemProp.http.nonProxyHosts=local.net|some.host.com

systemProp.https.keepAlive="true"
systemProp.https.proxyHost=host
systemProp.https.proxyPort=port
systemProp.https.proxyUser=username
systemProp.https.proxyPassword=password
systemProp.https.nonProxyHosts=local.net|some.host.com
```

### Docker
1. Native Docker
Depending on your OS, you have to edit a specific file (/etc/sysconfig/docker or /etc/default/docker).
Then, you have to restart the docker service with: sudo service docker restart.
It will not apply to systemd. See this page from docker to configure the proxy.

2. Docker with docker-machine
You can create your docker-machine with:
```shell
docker-machine create -d virtualbox \
    --engine-env HTTP_PROXY=http://username:password@host:port \
    --engine-env HTTPS_PROXY=http://username:password@host:port \
    default
```
Or you can edit the file ~/.docker/machine/machines/default/config.json.

### Java Proxy settings
```
http.proxyHost=host
http.proxyPort=port
http.proxyUser=username
http.proxyPassword=password
```

```bash
export JAVA_OPTS="-Dhttp.proxyHost=host -Dhttp.proxyPort=port -Dhttps.proxyHost=host -Dhttps.proxyPort=port"
```
