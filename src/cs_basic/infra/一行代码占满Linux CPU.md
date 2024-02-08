---
title: 一行代码占满Linux CPU
categories: Infra
tags:
  - Linux
date: 2020-10-12 01:58:59
---
```
for i in `seq 1 $(cat /proc/cpuinfo |grep "physical id" |wc -l)`; do dd if=/dev/zero of=/dev/null & done
```