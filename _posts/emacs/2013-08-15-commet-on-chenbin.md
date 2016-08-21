---
layout: post
title: 評陳斌前輩《一年成为emacs高手(像神一样使用编辑器)》
tags: [emacs, chenbin]
category: emacs
---
[http://%e4%b8%80%e5%b9%b4%e6%88%90%e4%b8%baemacs%e9%ab%98%e6%89%8b%28%e5%83%8f%e7%a5%9e%e4%b8%80%e6%a0%b7%e4%bd%bf%e7%94%a8%e7%bc%96%e8%be%91%e5%99%a8%29/](《一年成为emacs高手(像神一样使用编辑器)》)

## 介紹
這篇文章大約是中文界 Emacs 予新手的幾篇重量級入門概念文章。其中大部分的觀點我都認同，比方說下列幾點：

1. 讀官方教程(C-h t)
2. 不要背誦快捷鍵
3. 以興趣和急需解決的問題做切入點
4. 加入 Emacs 社區 (如：Google+ 上的國際 Emacs 社群)

唯一一個爭議點，也是這篇文章之所以飽受其他 Emacser 評論的點，在於他指出，必須「站在巨人的肩膀上」，也就是直接 clone 以然達到大師等級的配置來用。他推荐的是 Steve Purcell 的配置(請直接看陳斌前輩文章中介紹)，或者他本人的配置。

首先，我不推荐直接採用他人的配置。理由有二：

1. 如果其配置龐大而且沒有對應的詳細說明文檔，將會不知道有哪些功能可以選擇？哪些預設功能被改動？(快捷鍵或函數被defadvice了)。這點也是沒辦法的事：我自己的配置，我還要為他寫說明文件？
2. 配置往往不合我實際需要：例如，Steve Purcell 不使用 gnus 看郵件列表，也不寫 scheme 程式(他的設定檔有提供，但是是拿 lisp-mode 的通用設定來套用)，也不使用 dired-mode 來取代日常檔案管理員的工作(我可以在 Emacs 內用調用外部程式開啟檔案)。因此，我還得額外找配置，這又有點類似在巨大建築外面改建，問題重重。

這裡其實帶出了中文 Emacs 各種教學、套件介紹等一個缺失的環節，一個重要的環節。在看完 C-h t 的入門文檔之後，接下來呢？要做些什麼呢？

## 長期教程
因此，我這裡打算開始一項比較長期的教程計劃，也就是從 Basic tutorial 「之後」開始，描述你應該怎樣打造自己的 Emacs，讓它能夠貼近、滿足你工作上的需求。整體的學習順序大概如下：

1. 了解 Emacs 的包管理 (package management)。這是我從朋友 Carl Su 那邊得到的概念。就好像安裝好了一個新的 Linux 發行版，第一要學的就是海量軟體的安裝方式 (apt / yum / pacman 等等)，而 Emacs 也是同樣的道理。
2. Ido / Smex 的設定。 Emacs 有非常多的按鍵組合，實際上這些按鍵對應到的是背後執行這些功能的「elisp 函數」。在還不熟悉之前，建議採用 smex 來調用這些函數。由於它會自動提示你該函數的按鍵組合，若真的是常用的指令，再把他的按鍵組合背起來即可。(Emacs 不需要 cheat-sheet)
3. Elisp 設定檔的結構與撰寫方式。不要把所有設定通通丟到 ``.emacs`` 裏面，這是最要不得的早期教學錯誤！(同時指出，對於零散的小設定(如 ErgoEmacs 裏面常見的教學)要如何處理比較妥當。)

註：這一系列的文章已經完成，請見鐵人賽 [](2014 IT 邦 資訊鐵人賽 - emacs 新思維)。


## 建議

若是仍覺得陳斌前輩講的話很有道理(「直说了把,你是初学者,开始阶段应以学习模仿为主.这点怎么强调也不过分!」)，我改推荐你使用 Prelude 來取代 Steve Purcell 的設定！Prelude 的文檔比較詳細，額外的功能改善也不少。重要的是，作者常常寫部落格文章來介紹他裏面的程式碼及為什麼！(我也翻譯過幾篇裏面很有價值的設定，請見本邊陲小島其他文章)

## 參考資料：
1. [https://github.com/bbatsov/prelude](Prelude in Github)
2. [http://emacsredux.com](Emacs Redux)