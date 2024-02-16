---
title: "macOS:恢复系统默认的hosts文件"
date: 2023-10-09 08:32:21
tags: macos使用技巧
---

## 简介
有时候一些意外操作可能会破坏macOS的hosts文件，此时可以通过以下方式恢复。

## 操作

1. 输入下面的命令并按回车键，按照提示输入管理员密码，众所周知,在这个过程中输入过程中光标不会移动，输入完成后回车确认即可。

```bash
sudo cat <<EOF > /etc/hosts
##
# Host Database
#
# localhost is used to configure the loopback interface
# when the system is booting.  Do not change this entry.
##
127.0.0.1	localhost
255.255.255.255	broadcasthost
::1             localhost
EOF
```

该命令的作用是写入macOS默认的hosts文件内容。

2. 再运行下面的命令:

```bash
sudo chown root:wheel /etc/hosts; sudo chmod 644 /etc/hosts
```

3. 成功后，关闭该终端窗口，或者退出终端程序即可。