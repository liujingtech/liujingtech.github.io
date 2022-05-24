---
layout: post
title: 想开一个桌面级 ASoul 的 live2d 的 electron 项目
# subtitle: https://github.com/liujingtech/ASoulPetDesktop
tags: [ASoul,live2d,electron]
comments: true
---

> 最近在看资料的时候发现有个 web 版本的 live2d ，感觉很有意思。试了一下，把代码移植到了 electron 上面做了个实验性的桌面版本：https://github.com/liujingtech/ASoulPetDesktop

主要还是想通过桌面级的互动来增强陪伴感，毕竟现在的 Live2D 的模式比十年前的桌面宠物有更加生动的细节。虽然还是根据指令来触发序列动画，但是也许能通过动态获取信息来增强互动？

## BUG
1. 通过 `style="-webkit-app-region: drag"` 实现了拖拽，但是影响了本身的点击事件

## TODO
1. 通过爬虫捕获 ASoul 成员新的文字动态，并通过 Live2D 的台词/系统推送展示。(最想做的)
2. 开机自启动。()
3. 窗口置顶。
4. 托盘以及托盘菜单配置以上的功能。
5. 以及其他主要能增强陪伴感的功能。
6. github.io的个人站点应该也可以添加web版本的。
7. 吸附底部菜单栏？

## 目前的事情
考虑是否要用一个更加工程化的项目结构，比如使用主流的开发脚手架。这意味着会需要学习大量的新知识，比如 TypeScript，React,webpack?或者使用目前的代码先实现功能，毕竟从主界面来说，并不需要这些东西提供的特性。