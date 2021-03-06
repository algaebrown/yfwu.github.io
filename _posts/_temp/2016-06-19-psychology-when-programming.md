---
title: 創造，作為無名造物主的樂趣
category: thinking
layout: post
tags: [programming, psychology]
---
> 編程是最接近造物主的（不負責任的）活動

主要是在 Hackernews 上面看到一則討論 [Ask HN: What are some good peer-reviewed papers on psychology of programming?](https://news.ycombinator.com/item?id=11895384) 把文章貼給尚叡大大看，並討論之。底下條理化記述我們的想法。

## 關於編程時的心理學
提問者好奇幾件事情：（註解：``comprehension of programs`` 是編程時那種打字與思考同步的 feel，直白一點就是 **AHA**）

- What are some key factors that affect comprehension of programs? 
- How would those factors differ within each programming paradigm? 
- How much of a measurable impact does a particular syntax of a programming language (e.g. python vs. lisp vs. C-style) have on program comprehension?
- Is there good empirical evidence that particular programming no-no's (GOTOs, global variables, etc.) actively hinder program comprehension?

網友們怎麼回答呢？

1. 推薦閱讀
  1. 論文下載點 [*The Camel Has Two Humps*](http://wiki.t-o-f.info/uploads/EDM4600/The%20camel%20has%20two%20humps.pdf)
  2. 簡扼說明 [Separating Programming Sheep from Non-Programming Goats](https://blog.codinghorror.com/separating-programming-sheep-from-non-programming-goats/)
  3. 反對者 [Camels and humps: a retraction](http://www.eis.mdx.ac.uk/staffpages/r_bornat/papers/camel_hump_retraction.pdf)
  4. 我的看法：
2. 推薦搜尋
  1. ``software engineering research``
  2. ``psychology of programming``
  3. ``empirical research on computer language productivity``
  4. ``empirical research on programming methodology effectiveness``
3. 推薦閱讀
  1. [*Studying the language and structure in non-programmers’ solutions to programming problems*](http://www.cs.cmu.edu/~pane/ftp/PaneRatanamahatanaMyers2001.pdf) 
4. 推薦閱讀
  1. [*An Empirical Comparison of the Accuracy Rates of Novices using the Quorum, Perl, and Randomo Programming* Languages](https://ecs.victoria.ac.nz/foswiki/pub/Events/PLATEAU/Program/plateau2011-stefik.pdf)

## 符號邏輯，逼近真實的模擬

> 計算機不可能模擬與現實世界完全一樣的世界，因為它不能無損地模擬它自己。但是這只是錯誤的直覺，正如直覺上輸出自己的程序不存在，但是它們是確確實實存在而且可以平凡地構造的。

以上文章段落出自於 [日記](http://ppwwyyxx.com/static/student-festival/diary.txt)

- 數學作為逼近世界的手段？
  - 我覺得數學比較像**計算機設計**的子分支，因為所有的數學計算都能用電腦運作。反之，則無法肯定：圖靈完備計算機是一個能夠超出數學的計算構造嗎？
- Minecraft 的人工智慧模組
  - [Helpful Villagers](http://www.minecraftmods.com/helpful-villagers/)
- [張景中](https://zh.wikipedia.org/zh-tw/%E5%BC%A0%E6%99%AF%E4%B8%AD)：幾何自動證明
  - [《计算机怎样解几何题》](https://books.google.com.tw/books?id=ajkV-iB67KYC)
- 符號理論：
  - 一旦有了能夠不斷證明並不斷生成問題的機器，不斷證明與不斷生成問題的機器
  
## 假說自動產生 / 自動驗證

尚叡大大蒐集的四篇文獻，相當有趣，回答我關於生成問題與證明的一些困惑，來抓緊時間閱讀一下：

1. [Predicting Future Scientific Discoveries Based on a Networked Analysis of the Past Literature](http://dx.doi.org/10.1145/2783258.2788609)
2. [Context-driven automatic subgraph creation for literature-based discovery](http://dx.doi.org/10.1016/j.jbi.2015.01.014)
3. [Automated hypothesis generation based on mining scientific literature](http://dx.doi.org/10.1145/2623330.2623667)
4. [Study shows promise in automated reasoning, hypothesis generation over complete medical literature](https://www.bcm.edu/news/research/automated-reasoning-hypothesis-generation)

> 但我真的滿想知道機器怎麼對於真實世界的科學問題做出預測與解答方法的 proposal (e.g. 實驗設計)；就是提出問題，預測領域往哪裡走的意思。 - Shang-Jui Tsai 蔡尚叡
