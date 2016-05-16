---
title: R 平行化
category: r
layout: post
tags: [r, parallel]
---
底下記錄幾種我用過的平行化方法；這幾種方法當初是用在 Hazalyst 的 multiple nesting longitudinal statistics 計算上。

## Nested ``parallel::parLapply()``
[Can I nest parallel::parLapply()](http://stackoverflow.com/questions/8413188/can-i-nest-parallelparlapply)

``` R
library(parallel)

cl <- makeCluster(2)

inner <- function(x){
    pid <- Sys.getpid()
    name <- Sys.info()["nodename"]
    str <- paste("This is R running on", name, "with PID", pid, "!")
    return(str)
}

outer <- function(x, cores, funceval){
    require(parallel)
    mclapply(1:cores, funceval)
}

parLapply(cl, 1:length(cl), outer, 2, inner)
```

關鍵點：第一層使用來自 ``snow`` 的 ``makeCluster()`` 與 ``distributed memory technology``，第二層則是使用 ``multicore`` 提供的 ``mclapply()`` 與 ``shared memory technology``。不過這個方法我並沒有實驗成功。


## ``foreach`` with ``%dopar%``
