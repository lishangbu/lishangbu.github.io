---
title: Typora的一点小东西
date: 2024-02-16 07:44:50
tags: 软件和谐
categories: 软件
---



## windows/mac安装

通过下方官网地址下载软件并进行安装即可。

```bash
https://typora.io/
```

## windows/mac激活

安装完成后，如果是window系统，进入**typora**的安装目录(默认是`C:\Program Files\Typora`)下的 \resources\page-dist\static\js 目录，找到 **LicenseIndex**开头的文件。

如果是mac系统，默认情况下，直接执行以下命令定位:

```bash
open /Applications/Typora.app/Contents/Resources/TypeMark/page-dist/static/js
```

同样在目录下找到 **LicenseIndex** 开头的 Js文件。

用文本编辑器打开该文件，搜索

```javascript
e.hasActivated="true"==e.hasActivated
```

并将其替换为

```javascript
e.hasActivated="true"=="true"
```

实际上只要让e.hasActivated返回一个为真的布尔值即可，因此可完全可以替换成这样:

```javascript
e.hasActivated=true
```



（修改前，可将该文件备份一下，万一操作失误，可以进行恢复）



经过以上修改后，重启Typora后，点击左下角未激活，直接提示已激活。



macos可能会提示软件损坏，该开启任何来源开启任何来源，该移除`com.apple.quarantine`移除属性。
