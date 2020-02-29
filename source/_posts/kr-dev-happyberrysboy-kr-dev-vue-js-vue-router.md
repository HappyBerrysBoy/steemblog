---
title: '[kr-dev] vue.js 기본 구조(vue-router 포함)'
tags:
  - kr-dev
  - kr
  - jjm
  - busy
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)  안녕하세요 해피베리보이입니다.  오늘은 제가 요즘 열심히 공부하고 있는에 대한 개발관련글 남겨봅니다.  소스는 요즘 즐....."
date: 2019-03-25 13:01:42
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)

안녕하세요 해피베리보이입니다.

오늘은 제가 요즘 열심히 공부하고 있는 vue.js에 대한 개발관련글 남겨봅니다.

소스는 요즘 즐기고 있는 드럭워의 소스를 참고해서 보고있습니다.
___

#### 1. /public/index.html

- 기본적으로 public/index.html을 초기 페이지로 설정이 됨
- ```<div id="app"></div>``` 부분이 vue의 app이 마운트 될 부분

```
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <link rel="icon" href="<％= BASE_URL ％>favicon.ico">
    <title>vue-project</title>
  </head>
  <body>
    <noscript>
      <strong>We're sorry but vue-project doesn't work properly without JavaScript enabled. Please enable it to continue.</strong>
    </noscript>
    <h1>여기는 보이나요?1</h1>
    <div id="app"></div>
    <!-- built files will be auto injected -->
  </body>
</html>
```

#### 2. /src/App.vue

- vue는 하나의 .vue 파일에 하나의 template를 가지는 것이 기본
- 그래서 각각의 파일에 template에 해당되는 css도 해당 파일에 지정
- ```<router-view/>```부분은 /src/router/index.js 파일의 설정에 따라서 바뀌는 부분
- ```<HelloWorld msg="Welcome to Your Vue.js App haha"/>``` 부분은 vue의 다른 템플릿을 import 받아서 표시해주는 부분

```
<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <router-view/>  <!-- 여기는 router/index.js 설정에 따라서 page가 들어가는 부분 -->
    <HelloWorld msg="Welcome to Your Vue.js App haha"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default ｛
  name: 'apptest',
  components: ｛
    HelloWorld
  ｝
｝

</script>

<style>
#app ｛
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
｝
</style>
```


#### 3. router/index.js

- ```<router-view/>```부분에 들어갈 부분 설정 파일
- path 부분은 backend 단 route와 겹치면 설정이 제대로 되어 있지 않으면 문제가 발생가능
- path를 지정해주고 component를 설정해주면, 주소창에 path값이 바뀔면 해당 component가 설정

```
import Vue from 'vue'
import Router from 'vue-router'
import HelloWorld from '@/components/HelloWorld'
import Test from '@/components/Test'
 
Vue.use(Router)
 
export default new Router(｛
  routes: [
    ｛
        path: '/a',
        name: 'HelloWorld',
        component: HelloWorld
    ｝,
    ｛
        path: '/',
        name: 'test',
        component: Test
    ｝
  ]
｝)
```

___

이정도 구조만 알아도 간단한 페이지를 구현하는 것에는 문제가 없을 듯 합니다.
vue template 사용법은 또 별도로 공부해서 포스팅 해보자!!!

요즘 개발 공부 안하다가 보니까 은근히 복잡하군요..
이게 webpack이랑 babel, lint 등 설정과 겹치니 더 헷갈리는 부분 ㅠㅠ

암튼 열공합쉬다!!!
감사합니다!!