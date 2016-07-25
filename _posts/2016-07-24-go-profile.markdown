---
layout: post
title:  "golang profile介绍"
date:   2016-07-24 13:16:54
categories: golang
tags: golang, profile
excerpt: golang profile
---

## golang profile
    
```
import _ "net/http/pprof"

func main(){
        go func() {
             log.Println(http.ListenAndServe("localhost:6060", nil))
        }()
}
```
再执行

1. CPU的profile信息
```
go tool pprof http://localhost:6060/debug/pprof/profile
```
2. MEM的profile信息
```
go tool pprof --alloc_space http://localhost:6060/debug/pprof/heap
```

会进入30s的采样


随后(pprof):web 即可生成调用消耗的svg图


PS：生成svg图需要安装graphviz
