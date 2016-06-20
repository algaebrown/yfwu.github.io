---
title: 招募醫學計算機視覺讀書會成員
category: medical
layout: post
tags: [matlab, opencv, python, dicom]
---
目標：系統性地學習**醫學影像處理**相關的**計算機視覺**知識，嘗試以程式語言處理醫學影像。雖然說是讀書會，我個人感覺起來比較像**同好會** XD

## 數學
**我每次看到有學弟妹們想要玩程式設計，只要不是搞前端或資安，而是想要跨醫工（影像、資料科學、訊號分析），我一律建議先把數學學好。**學哪一種程式語言不重要，因為這幾個領域大部分都是使用別人的工具，程式都不會太長（要能夠開發自己的算法是不太可能的事情）。**重點在於：要怎麼選擇正確的算法、函式庫？要怎麼分析資料並正確的理解該輸入甚麼？輸出的結果又如何判讀？**急著開始學寫程式是事半功倍的！至於要學哪些呢？

1. **微積分**：高等數學的基礎，也是我學習統計學上的一道大門檻 :P
2. **工程數學**：玩建模必學
3. **線性代數**：大數據與影像處理不可或缺之工具。

至於用甚麼當教材？<del>底下不是廣告！</del>我個人喜歡[劉明昌老師](http://m.sanmin.com.tw/product/index/99t155t10l103b52k103q71l112z130busguwz130mxx)的講義。工數、線代我也都是讀他的書。對於沒時間讀原文書的同學，我覺得讀**考研講義**是最快最強的方法！（就好像讀老趙的解剖學一樣訴程、有效、強大）

## 語言
醫學影像庫最多的大概還是 **matlab**。而 Python 與 R 有崛起之趨勢。我本人以前大三的時候也是很會操作 matlab 的！（如下圖）。可能使用的教材是 Wiely-ISTE 的 *Digital Signal and Image Processing using MATLAB*（共三大本）。或者是比較輕薄短小的儒林《數位影像處理 Matlab》

![matlab](/assets/matlab.jpg)

這是傅立葉轉換元。當初的 code 跟報告投影片還在。可是我已經看不懂了（淚目）。怎麼獲取 Matlab ... 暗黑教學網路上很多啦 XD 電子書某俄國網站上也很多，就自己找。<del>找不到就不要學惹，不然就乖乖花錢買唄</del>

## 我的想法
底下是循序漸進的概念

1. 在了解數學工具和程式語言基本語法後，可以開始實作各種練習。（所需時間：兩個半月）
2. 了解醫學影像的檔案格式及協定（如 [DICOM](https://zh.wikipedia.org/wiki/DICOM)）
3. 了解醫學影像如何讀取、修改、儲存（2 + 3 所需時間約兩周）
4. 了解常用的影像處理原理（所需時間：兩個月）
5. 使用 ``OpenCV`` 這個影像處理函式庫（所需時間：兩個月）
    1. [MATLAB and OpenCV](http://www.mathworks.com/discovery/matlab-opencv.html)
    2. 註：[Python and OpenCV](https://opencv-python-tutroals.readthedocs.io/en/latest/)
    3. 註：[R and OpenCV](https://www.openhub.net/p/r-opencv)
        1. [21 個醫學影像分析的 R 軟體套件](http://dataology.blogspot.tw/2014/09/21r.html)
5. 邀請與醫學影像處理相關的工程師來分享與討論

## 資料集
1. [DICOM library](http://www.dicomlibrary.com/)
2. [CVonline: Image Databases](http://homepages.inf.ed.ac.uk/rbf/CVonline/Imagedbase.htm)
3. [ImageProcessingPlace.com](http://www.imageprocessingplace.com/root_files_V3/image_databases.htm)
4. [Cornell Public Image Databases](http://www.via.cornell.edu/databases/)
5. [Materialise](http://uc.materialise.com/mimics/resources/datasets)
6. [Open-Access Medical Image Repositories](http://www.aylward.org/notes/open-access-medical-image-repositories)
7. [Computer Vision Test Images](https://www.cs.cmu.edu/~cil/v-images.html)