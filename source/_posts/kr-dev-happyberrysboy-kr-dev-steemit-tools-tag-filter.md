---
title: '[kr-dev] Steemit Tools, Tag Filter 기능'
tags:
  - kr-dev
  - busy
  - mini
  - jjm
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://ipfs.busy.org/ipfs/Qman2EX2PHQ4YpS5QRttNh6yBApcQQVc3YD2iheeThsdS8\" />\r\n  안녕하세요 해피베리보이입니다. 개발을 좀 하다보니 시간이 너무 늦었네요.. ㅠㅠ  얼른 개발된 부분 보여드리고 자러가야겠습니다.  금일 추가한 기능은 Tag Filter 기능입니다. 간략히 설명드리자면, Tag를 등록하면 해당 Tag가 현재 보여지는 화면에서 사라지도록 만들었습니다. 가끔 게임종류나 특정 태그들을 보기 싫어하시는 분들이 있길래 한번 만들....."
date: 2019-05-15 03:43:18
---

![](https://ipfs.busy.org/ipfs/Qman2EX2PHQ4YpS5QRttNh6yBApcQQVc3YD2iheeThsdS8)

안녕하세요 해피베리보이입니다.
개발을 좀 하다보니 시간이 너무 늦었네요.. ㅠㅠ

얼른 개발된 부분 보여드리고 자러가야겠습니다.

금일 추가한 기능은 Tag Filter 기능입니다.
간략히 설명드리자면, Tag를 등록하면 해당 Tag가 현재 보여지는 화면에서 사라지도록 만들었습니다.
가끔 게임종류나 특정 태그들을 보기 싫어하시는 분들이 있길래 한번 만들어 보았습니다.

동영상으로 촬영하려니 또.. 맥북에 프로그램이 좀 많이 구리네요 ㅠㅠ
캡쳐 화면으로 대신하겠습니다.

##### 메뉴는 3번째 눈모양 아이콘으로 등록
- 클릭시 우측에 Tag를 등록 할 수 있는 화면이 나타남

![image.png](https://ipfs.busy.org/ipfs/QmagoQYyPZPZ2bVgNrrcdWh749fAQTfCmJDW6AMCtB3TB1)

##### 보기를 원치 않는 태그 등록
- 현재 steem-engine과 mira 태그를 달고 있는 포스팅이 2개가 존재함.
- Tag Filter에 Tag를 등록하면 아래아래 사진처럼 포스팅을 가려줌.
![image.png](https://ipfs.busy.org/ipfs/QmaQansYJdXZHy6feJesgrjwHzLnFxscQEeuRrLzdwV2x7)

##### 쫜!!
![image.png](https://ipfs.busy.org/ipfs/QmSTgfsXoKNrjspKZzPZq5ZJWRuwkVXujf8bsfevCkPiK1)

##### 작동 원리
- Refresh 되고 난 뒤 Steemit Tools 프로그램이 실행 된 이후에 필터링 처리
- 코드 추가시 3초마다 필터링 재실행
- 코드 추가 후 별도의 Refresh 없이 바로 실행

##### 문제는 아직 받는 곳이 없습니다. 아직 배포전이거든요..!!! 기능 몇개만 더 추가하고 일단 베타버전(지겨운 베타..)을 출시하도록 하겠습니다.

와웅 늦었당 자야겠어요!! ㅠㅠ 
다들 지금부터 돼지가 똥밭에서 놀고 있는데 산신령이 나타나서 소원을 들어 준다고 하는 꿈 꾸시길 바랍니다!!

굿굿밤!!

