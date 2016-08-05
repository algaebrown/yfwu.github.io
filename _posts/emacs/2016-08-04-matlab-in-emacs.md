---
title: Matlab in Emacs
layout: post
tags: [matlab, emacs, terminal]
category: emacs
---
![Matlab in Emacs](/assets/matlabemacs.png)


最早的文章寫於 ``2013-07-31``，好久沒有用 Matlab 啦，最近因爲去陽明光電所接了幾個腦造影專題都是 Matlab，決定拾起當年的筆記。

## 當年的筆記！
成功的於 emacs 中執行 matlab 交互介面(簡稱為 matlab-shell，也就是一般常見一進入 matlab 那個 >> 提示符號的視窗)，以及開啟副檔名為 .m 的 matlab 程序存檔(一個 major-mode：matlab-mode )。至於除錯的部份，因為我只是用這個東西處理「醫學影像處理」課程中所指定的簡單題目，因此尚未嘗試。(python 的除錯工具 pdb 我也還沒深入研究，這應該也是儘快要掌握的)。有一些額外的配置，但因為我不是靠 matlab 吃飯的，所以也沒有特別深入研究，不過既然已經成功啟動了，我想配置就不那麼困難囉！

最後面會列出我的參考資料，還有諸位必須先取得 Matlab for UNIX 的程式(2013b 安裝成功，取得方法請上網找找，礙於法律這邊不公佈 XD)

**更新**

1. 我現在是神祕管道取得的最新版 2016a for Unix :P
2. 不曉得 matlab-mode 的 auto-complete / debugging 現在做的怎麼樣了 XD

## 安裝 Matlab

1. 首先掛載 iso 檔案，並且執行腳本 install.sh (若無法執行，請 ```chmod +x install.sh```，會需要輸入驗證伺服器文件(license.dat)以及鑰匙(key)，一般可在光碟內其他資料夾找到。
2. 會出現 java 寫成的安裝程式，安裝到指定的位置(沒記錯的話他的目標是 ```/usr/local/MATLAB/R2013a```，你可以自己更改成喜歡的沒差)
3. **(此步驟重要)** 將 ```/usr/local/MATLAB/R2013a/bin/matlab``` 建立 symlink 到 ```/usr/bin```，不然會出現 Searching for program: no such file or directory, matlab
4. 之後 Emacs 的 mode 會從這個 symlink 連到 matlab 解釋器。
5. 需要注意的是：可能是官方支援度不好？我的 matlab 的 java 介面主程式啟動之後會自己關掉，然而 emacs 裏面用 matlab-shell 倒是非常穩定。

**補充**
1. Matlab 吃舊版本的 libncurses，需要設定
   ``` shell
   sudo ln -s /usr/lib/libncursesw.so.6 /usr/lib/libncursesw.so.5
   ```

## 安裝 matlab-mode

直接使用 el-get 安裝！

### 舊做法
1. 前往本 cvs 存放點取得所需.el 檔案
2. 解壓縮到~/.emacs.d 裏面你喜歡的資料夾
3. 把下列 elisp 指令加到 init.el 或者其他的設定檔中：
   ``` matlab
   (autoload 'matlab-mode "matlab" "Matlab Editing Mode" t)
   (add-to-list 'auto-mode-alist '("\\.mquot; . matlab-mode))
   (setq matlab-indent-function t)
   (setq matlab-shell-command "matlab")
   ```
4. 重新啟動或者 eval-current-bufffer 之後，開啟一般的檔案如：function.m，會進入 matlab-mode 可以編輯。
5. 以 ```M-x matlab-shell``` 可以啟動交互畫面，就跟主程式一樣沒有差別！
6. 補充說明：shell-command 設定下去之後，```C-c C-c``` 可以把整個 buffer 送進去執行，而 ```C-c C-r``` 則是將選定的區域送入執行

**補充**
1. 需要確定 matlab 啓動腳本存在於 ``$PATH`` 內.

## 參考資料

1. [在 Linux 下安裝 64 位元 matlab (2013a 新資料)](http://blog.sbw.so/Article/index/title/64%E4%BD%8DLinux%E5%AE%89%E8%A3%85Matlab-2013a%E5%AE%9E%E7%94%A8%E6%95%99%E7%A8%8B.html)
2. [官方部落格說明(英文)](http://blogs.mathworks.com/community/2009/09/14/matlab-emacs-integration-is-back/)
3. [Emacs-wiki](http://www.emacswiki.org/MatlabMode)
4. [Matlab-emacs 运行 matlab 程序出错.不能调用 matlab 命令行模式 ](http://blog.csdn.net/loveaborn/article/details/8754099)
4. [Matlab libncurses bugfix](https://bbs.archlinux.org/viewtopic.php?id=202575&p=2)
