---
title: Matlab 中的函數與檔案管理
layout: post
category: matlab
tags: [matlab, function, project]
---
跟女朋友討論 Matlab 專案的資料夾結構，我提到不少程式語言都是把類似用途的函數放在同一個檔案內，然後通過 TDD（test-driven development）的流程來控管，並且在檔案互相呼叫下，可以有效以 **namespace** 的特性避免衝突。但是，matlab 似乎沒有這種共能？於是使得目錄下面有數十個 matlab 的 ``.m`` 檔案。這篇嘗試深入瞭解一下這個問題及是否有 namespace 的替代方案。

## Local Functions

以官方指引 [local functions](http://www.mathworks.com/help/matlab/matlab_prog/local-functions.html) 爲例，文章舉了下面的例子：

``` matlab
function [avg, med] = mystats(x)
  n = length(x);
  avg = mymean(x,n);
  med = mymedian(x,n);
end

function a = mymean(v,n)
  % MYMEAN Example of a local function.
  a = sum(v)/n;
end

function m = mymedian(v,n)
  % MYMEDIAN Another example of a local function.
  w = sort(v);
  if rem(n,2) == 1
    m = w((n + 1)/2);
  else
    m = (w(n/2) + w(n/2 + 1))/2;
  end
end
```

在上面的例子中，三個函數均存在於 ``mystats.m`` 這個檔案內。其他檔案想使用的話，不需要有 ``import`` / ``using`` / ``include`` 等動作，只需要直接呼叫 ``mystats`` 即可！加上說明，可知道：

1. Matlab 會將每個 ``.m`` 檔案讀入
2. 只有其中第一個會被讀取，剩下來的都是供第一個函數使用的 local functions


## Namespace in Matlab
