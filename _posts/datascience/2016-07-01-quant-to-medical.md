---
title: 移植既有工具到醫學上
category: datascience
layout: post
tags: [quant, medical]
---
最近一次 H4 聚會（2016/06/30）討論完 Clojure 讀書會之後和尚未認識的宜潤大大聊天，簡單的討論上個周六的交易未來式（[演講記錄](http://yfwu.github.io/datascience/2016/06/26/quant-speech.html)），除了討論諸講者實際內容的優缺點外，也討論了我一些猜想。

我的猜想主要是關於移植量化金融相關的工具來醫學領域。之所以會這樣講，是因為讀了《華爾街的物理學》給我一種想像，即最新的工具、建模側略都會從華爾街那邊流出 A_A 不過宜潤大大說，我更應該直接讀學界關於訊號分析的專書及期刊（如 Elsevier 的[《Signal Processing》](http://www.journals.elsevier.com/signal-processing)，但這對於學醫的我來說又太難了）。

關於怎麼入手這些東西之後再說 :P 不過，正如同最近在看的一本[《圖解機器學習》](http://m.sanmin.com.tw/product/index/005093606)裡面提綱挈領式的從最小二乘法出發，討論傳統的機器學習手段（迴歸、分類、聚類、降維），同時以簡明扼要的 Matlab 演算法來闡明數學原理，我想我們也應該找一本好一點的訊號分析課本來讀才是 XD



## 討論內容
我們共討論了三個面向。因為時間很短，加上也沒有預先特別準備，所以只簡單談論了一些想法：

- 指標
    - 技術分析有很多奇奇怪怪的指標，如著名的五種「均線 MA、隨機震盪指標 KD、相對強弱指標 RSI、指數平滑異同移動平均線 MACD、乖離率 BIAS」五大技術分析指標。在 hemodynamic 相關的研究裡面，也有相關的構想！（參考讀物：[《Computational Hemodynamics – Theory, Modelling and Applications》](http://www.springer.com/us/book/9789401795937)，這是去年的新書，看了一下，這應該是全新的領域，估計之後**會有非常多的專科知識被電腦化並以大量數據驗證**）
    - 金融界會有各種奇怪的指標，有很多工具是建構在這種東西上面。醫學上面不曉得有沒有類似的對應物。例如有些工具是評估五日均線，但是醫學上似乎沒人把五日血壓平均起來？這樣的指標是否可以直接移植過來用？如果可以，意義要怎麼解讀。那些技術分析專家說得頭頭是道的**反彈、驟降力道**是不是也能拿來預測血壓遽烈變化呢？
- 樣本量
    - 同一支股價的時間長度可以幾千天，有很多資料點。反過來說一個病人，大多數都是住院幾天、十幾天，資料點最多一天四次。除非 ICU 才有連續監測，可能在重症照護上才有利基。要把模型外推到一般人尚有很大改進空間！
    - 後來臉書聊天的時候，尚叡大大跟我問到一般的長照居家是不是也算是大量樣本量適合的情境。之前在[〈下一代，醫療〉](http://yfwu.github.io/startup/2016/04/28/future-medicine.html)內也有與劉文德醫師談過。除了雜訊量非常驚人外，既有的醫學知識也缺乏「平日觀察」這一特定領域知識。例如：還沒有心絞痛之前就預測心絞痛，該用怎樣的指標呢？
- 通道
    - 通道是通過一系列統計手段建立一個上下標準（例如常見的[布林通道 Bollinger Bands](https://en.wikipedia.org/wiki/Bollinger_Bands)），當信號曲線以某種模式超過或接近上下標準時，就算有「信號」，可以看成值得介入的情況正要發生。
    - 我跟他在想這種工具似乎就有轉換過來的空間；例如血壓的連續監測，如果我們觀察到一個血壓可能驟降的信號，就能夠在病人休克之前做處理。當然，不可能直接套用，但是這樣的嘗試似乎還沒有人作過？（完全沒有文獻）

## Neuro-Fuzzy

這篇是之前寫的短文。放在這邊做為對機器學習技術開始在醫療領域具體化的記錄：

在《榮總護理》上面看到一篇文章〈病歷回溯法比較重症病人不同血糖控制法血糖控制之成效－以某醫學中心加護病房為例 〉，覺得相當有趣。這篇文章是以加護病房 APACHE II 分數 > 20 以上的病人做為研究對象，探討以 Dazzi 於 2001 發展的 Neuro-Fuzzy Network Serum Glucose Control System（註1）應用於重症病患的血糖控制上。

不過不諱言，這篇研究的缺點略多。例如：病患的疾病種類、升壓劑劑量、腎病程度（註2）等都算是應較正而未較正的重要影響因子（有較正糖尿病跟類固醇劑量）。第二，雖然檢力計算上並無大問題，然而在統計方法上，是以年齡性別做分組再跑觀察期血糖值「超過150mg/dL - 未超過 150mg/dL」的 ratio 去執行差異的 ANOVA 比較。我個人好奇多日血糖值**變化狀況**的差異（這才是重點），是否應該以迴歸統計方式來計算。

不過，這種工具應用於臨床照護上到是才剛起步，對於高榮護理部願意進行這樣的嘗試還是覺得值得鼓勵！

1. Dazzi D, Taddei F, Gavarini A, Uggeri E, Negro R, Pezzarossa A. The control of blood glucose in the critical diabetic patient: a neuro-fuzzy method. J Diabetes Complicat. 2001;15(2):80-7.
2. Abe M, Okada K, Soma M. Antidiabetic agents in patients with chronic kidney disease and end-stage renal disease on dialysis: metabolism and clinical practice. Curr Drug Metab. 2011;12(1):57-69.