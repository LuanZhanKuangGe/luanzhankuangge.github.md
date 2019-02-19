---
title: 安卓程序性能分析工具
date: 2019-02-19 17:23:33
categories: 技术教程
tags:
- Android
- Profiling
---

# Simpleperf

* 官方提供的性能分析工具，能监控cpu cycle，cache miss等系统事件，也能找出最耗时的函数。
* NDK自带，在根目录Simpleperf文件夹内.
* 查看可监控事件: ./simpleperf list
* 监控事件：./simpleperf record -o ./perf.log -e your_event ./your_app your_app_arg
* 查看结果：./simpleperf report -i ./perf.log --sort symbol
* 效果如下：

``` bash
Cmdline: /data/local/tmp/simpleperf record -p 4281 --duration 30 -o /sdcard/perf.data
Arch: arm64
Event: cpu-cycles (type 0, config 0)
Samples: 106529
Event count: 38804869540

Overhead  Sample  Symbol
10.45%    10993   NEON_ChromaInterpolate4_H00V00_8
5.94%     6238    NEON_LumaInterpolate4_H03V03
5.10%     5354    RVComFunc::DBFShiftedProcess8x8
3.55%     3722    RVComFunc::deblockCUTree
``` 
*  记得使用带符合表的执行文件(obj目录下那个)，否则Symbol显示不了函数名.