---
title: 計算機怎樣解幾何題
category: clojure
layout: post
tags: [geometry, clojure, AI]
---
雖然最近深度學習、類神經網路佔據了[人工智慧](https://en.wikipedia.org/wiki/Artificial_intelligence)領域的全部版面，但其實人工智慧還有非常多面向的研究方法。Symbplic AI 或叫 classical AI 是一種嘗試以符號處理抽象化人類思維並且計算機化的過程。而在當時的研究世界裡面，有一種程式語言，叫 **Lisp**，以程式碼/資料結構同像性 homoiconic、快速開發 prototype 的能力及諸多符號處理的有力工具成為該時人工智慧研究首選語言。

本文嘗試將張景中老師的著作《計算機怎樣解幾何題》的概念以 [Clojure](https://en.wikipedia.org/wiki/Clojure) （Lisp 的方言）來展示。


## 