---
title: 使用 Emacs 控制 Mozilla Firefox
tags: [emacs, firefox]
layout: post
category: emacs
date: 2016-01-13
---
[Github Repo](https://github.com/RenWenshan/emacs-moz-controller)

記錄下流程及一些容易忘記的重點。

## 安裝 emacs-moz-controller
1. 通過 el-get 或 package.el 安裝咯！
2. 手動安裝的朋友記得去下載 ``moz.el`` 並加入 load-path 中的目錄，然後 require；之後才 require ``moz-controller``

## 安裝 Firefox MozRepl
1. 上 addson.mozilla.org 找這個套件並安裝
2. **Go to Firefox Tools menu (to make it visible, press F10 or Alt-T – depening on your platform) and select MozLab → Start MozRepl.**
    1. 這步最重要，要記得啟動 REPL ... 我卡在這裡卡了一陣子
3. 之後就可以盡情享受了！

## 按鍵

| function               | name                            | keybinding |
|:-----------------------+:--------------------------------+:-----------|
| get current tab’s url  | moz-controller-get-current-url  | C-c m l    |
| refresh                | moz-controller-page-refresh     | C-c m R    |
| scroll down            | moz-controller-page-down        | C-c m n    |
| scroll up              | moz-controller-page-up          | C-c m p    |
| zoom in                | moz-controller-zoom-in          | C-c m +    |
| zoom out               | moz-controller-zoom-out         | C-c m -    |
| zoom reset             | moz-controller-zoom-reset       | C-c m 0    |
| switch to previous tab | moz-controller-tab-previous     | C-c m b    |
| switch to next tab     | moz-controller-tab-next         | C-c m f    |
| close current tab      | moz-controller-tab-close        | C-c m k    |
| view page source code  | moz-controller-view-page-source | C-c m u    |
