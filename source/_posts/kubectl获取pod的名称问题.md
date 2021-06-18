---
title: kubectl获取pod的名称问题
date: 2021-06-18
tags: 笔记
---
想要重启kubectl中的pod，需要通过：
kubectl get pods
如果有多个pod，而且每次重新部署后pod会自动生成不同的名字，这个时候可以给deployment文件添加标签
![](https://cdn.jsdelivr.net/gh/hzcy/cdn@main/1624014823000.PNG)
添加标签后可以使用：
 kubectl get pod -l app=“标签名”
来获取
这样可获取命名空间下的特定pod
比如重新部署某一个pod：
 kubectl get pod -l app=appname -n namespace -o yaml | kubectl replace --force -f -