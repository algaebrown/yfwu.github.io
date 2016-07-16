---
title: 台灣資料科學年會主議程（一）
category: datasciencee
layout: post
tags: [datascitw]
---

## A Culture of Big Data: Case Studies from Google
紀懷新 Google Research Scientist

- **Data Science = Measurement + Impact**
- Case 1: Wikipedia's Growth
    - 例如：怎麼量測維基百科的「整體性」的成長呢？
        - 將文章數量的成長繪圖出來，發現圖形是 exponential growth 的 pattern。能夠以社會科學已知的 exponential growth 的機轉來解釋嗎？
        - 如果改以活躍的編輯者的數量來評估呢？
    - [Preferential attachment: edits beget edits](https://en.wikipedia.org/wiki/Preferential_attachment)
        - 但這情境只有在無限環境才有...
        - 現實情境是 [logistic growth model](https://services.math.duke.edu/education/ccp/materials/diffeq/logistic/logi1.html) = 資源到頂時，競爭最激烈；而擁有較多資源的個體，對於資源較少的個體競爭優勢更明顯，從而導致分布不均
    - 用 「new articles per unit time」 來測量維基百科，發現發展大不如前。這樣的結論，對嗎？
    - **其實人類的整體知識是增長的：carrying capacity as a function of time!**
        - 但，如何評估上述的議題呢？目前這還沒有答案，值得去研究依然持續增長的 logistic growth model
    - 但是就算知道問題，維基基金會卻說「That's interesting」 XD 沒辦法造成 impact
- Case 2: Google+ Communities
    - 最難評估的是**一開始增長時**的模型
    - 問卷調查：*What do people get out of online communities?*
        - 有人說，參加社群的目的是為了得到「資訊 information consumption」，有人要得到的是「連結 social ties」
        - 這是兩種不同的假說。怎麼驗證呢？
    - 引入 **Triangle closure counting** 的概念
        - 不單純用「圖形的邊 edge」來評估！
        - Triangle closure 可以用來計算 social network graphing analysis 有多密集
    - 計算「社群成員大小」與「社群成員社交網路的 triangle closure」
        - 有一些 outlier。為什麼呢？
        - 區分出兩類**社群模式**
            - Photographers 同好 *plazas*
            - Meeting places 資訊分享 *topic boards*
        - [Third places](https://en.wikipedia.org/wiki/Third_place)
        - Communites with fewer edge and posts more than comments，就可以歸類為 topic boards，否則比較像 plazas
    - 最後，以問卷來驗證 hypothesis（mix method - 量化數據與質化問卷）
- Case 3: Google Translate
    - 要真正造成 impact，還是得真正去做。
    - How to reduce isolation of culture group - through Google translate?
        - G+ 相比於 Twitter，更加的 lumpy cluster，群組之間的 gap 更大！
        - 於是，有了一個將 Google translate 結合入 G+ 的計畫
    - 將功能加入後，進行 7-day holdback experiment，發現很多有趣的 behavior
        - 例如：封鎖增加了！因為現在看得懂那些廣告訊息

感想：很有趣的演講！用一句話總結主題，就是「如何測量模式未知的資料，並理解資料來源的內在變化」。例如，怎麼樣測量維基百科現在的增長？怎麼樣測量 G+ 社群的增長機制？不過在前兩個案例裡面，對於如何將測量過的結果去製造 impact 或者改變公司經營策略則沒著墨。第三個案例則是討論將 Google translate 加入 G+ 的整個故事，從事前測量到加入後的評估、後續研究等。

## 善用資料改善線上教務:誠致教育
呂冠緯、蘇倚恩

## 隨機對照實驗在公共領域的應用
謝宗震

## 一個賭徒的告白二：交易策略建構與分析
吳牧恩

## 數位廣告大數據
趙國仁

## 如何備料：資料的抓取、清理及串接
李慕約

## 資料科學與防疫應用的結合：以登革熱防治為例
莊坤達
