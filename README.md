## lottery-num，抽奖应用数字版：

学习 HbuilderX、uni-app 环境搭建、开发发布流程；

学习 uni-app开发细节。

使用了 vue.js 做框架，代码可以发布到iOS应用、Android应用、H5、各种小程序。

官网：https://uniapp.dcloud.net.cn/quickstart-hx.html


对一个普通的Vue项目来说：
> 第一步 利用 HBuilderX 搭建项目雏形

> 第二步 根据项目的功能设置页面的路由


### UNI与Vue的区别：

1. 开发使用Vue单文件组件：在 index.vue 使用<template>、<script>、<style>

2. 在开发使用中，标签靠近小程序使用规范：
  
* div、p、ul、li 改成 view；
  
* span、font 改成 text；
  
  1. a 改成 navigator；
  
  1. img 改成 image； 
  
  1. uni-ui 新增了一批手机端常用的新组件，如：日期格式化、左右滑出的抽屉、可区域滚动视图容器、图标、进度条等；
  
  1. 而 vue使用web端的标签.

3. 接口能力靠近小程序规范，使用的内置的API，用JS实现路由的跳转，数据的存储等，

如：uni-app：uni.navigateTo 路由与页面跳转；uni.request 网络请求。

4.  数据的绑定与事件处理同 Vue.JS规范，同时补充了APP及页面的生命周期，

如：APP.Vue中 onlaunch、onshow等。

5. 使用flex布局进行开发，单位是rpx（rpx是微信小程序独有的、解决屏幕自适应的尺寸单位，通过 rpx 设置元素和字体的大小，小程序在不同尺寸的屏幕下，可以实现自动适配）。

6. Uni-app可以编译到（头条，支付宝，微信，QQ，百度）小程序，安卓版，ios版，h5版。

 通过打包实现一套代码多端运行；vue在web上是为单页应用而生的，在app上，单页应用会卡死。
