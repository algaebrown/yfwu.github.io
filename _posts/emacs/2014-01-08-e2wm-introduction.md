---
layout: post
title: Package Introduction - e2wm
category: emacs 
tags: [emacs, package]
---
__E2wm: Equilibrium Emacs Window Manager__

[Github Repo](https://github.com/kiwanami/emacs-window-manager)

當我們嘗試要把 emacs 改造的有如 IDE 一樣多視窗時，會面臨到許多問題。

1. 對應的視窗功能如何一次行啓動，如標籤（指由 etag/ctag 生成的 TAGS）、檔案管理、自動補全，甚至是想要像 sublime 一樣有個小視窗可以預覽？
2. 這些視窗又要如何安排？能否不要手工調整大小、位置？

在 emacs 中確實有些已經實現的解決方案，如 cedet / ECB，就是一批很強大的工具組合。關於他們的說明可以參考底下鏈結：

1. [Emacs Code Browser](http://ecb.sourceforge.net/docs/index.html#Top)
2. [Cedet](http://cedet.sourceforge.net/)

由於這些工具其工作模式（如，顯示那些窗口，用什麼做 backend，是固定的）變更不易，因此如這篇文章：[emacs 中不使用 ide 的開發方式](http://sigmundtzeng.blogspot.tw/2013/02/emacside.html) 中提到，可利用高效的窗口管理搭配 shell-mode，打造更適合的環境。但是，這樣還是太麻煩而且太累了。本文要介紹的工具，便是爲了滿足這樣的需求而來的！



