---
title: 重置macOS Launchpad 设置
date: 2024-04-19 03:20:08
tags: macos使用技巧
---

```bash
# 重置 Dock 图标数据库
rm ~/Library/Application\ Support/Dock/*.db && killall Dock
# 重置 Launchpad 图标数据库
defaults write com.apple.dock ResetLaunchPad -bool true && killall Dock
```


完成以上操作后，Launchpad 图标布局已经恢复默认设置，苹果官方提供的 App 都被重新排列到 Launchpad 第一屏幕中，然后根据自己的需要来进行重新排列 App 即可。
