---
title: 추천글 개발 작업 완료(아마도?)
tags:
  - sct
  - sct-kr
  - sct-freeboard
  - union
  - zzan
  - palnet
  - liv
  - dblog
  - mini
author: happyberrysboy
categories: life
excerpt: "<img src=\"https://steemitimages.com/0x0/https:/\" />\r\n/cdn.steemitimages.com/DQmeVyCnkva2SjkjT5mk9XPo2BJzbK7szFE1pDqqAHrSBsC/WHALE_TITLE_COLORED_LOW.jpg)  안녕하세요 햅뽀이입니다.  지난 주 부터 작업하고 있던 추천글 메뉴 추가 작업의 끝이 보이는 것 같습니다.   #### 구현 방법은 대략 아래 3가지로 구성됩니다. 1. 추천글 ....."
date: 2019-12-10 23:21:39
---

![](https://steemitimages.com/0x0/https://cdn.steemitimages.com/DQmeVyCnkva2SjkjT5mk9XPo2BJzbK7szFE1pDqqAHrSBsC/WHALE_TITLE_COLORED_LOW.jpg)

안녕하세요 햅뽀이입니다.

지난 주 부터 작업하고 있던 추천글 메뉴 추가 작업의 끝이 보이는 것 같습니다. 

#### 구현 방법은 대략 아래 3가지로 구성됩니다.
1. 추천글 메뉴를 추가한다.
2. 스판 운영진에서 등록한 계정의 글만 표시된다.
3. 등록된 계정에서 **특정 태그**를 사용 한 글만 표시되도록 한다.
4. 추천저자만의 특별한 **뱃지**를 표시한다.

여기서 메뉴를 추가하는 것 까지는 쉬운데 난관이 하나 있었습니다.

바로 스팀 API에 **특정 계정 AND 특정 태그** 조건으로 글을 조회 할 수 있는 API가 없었던 것이었습니다. 그래서 그 외에 다양한 방법들을 사용해 보았는데, 더 많은 데이터를 조회해서 많은 필터링을 거치는 방법을 하다보니 부하는 더 커지고 속도도 현저히 느려지는 현상을 맞이 했던 것이었죠.

현재 니트러스 사이트 메인개발자에게도 문의는 해보았지만, 해당 API는 없다는 말만 돌아 왔을 뿐이었습니다. 그렇게 시간이 흐르고... 오늘 스팀 API 아이쇼핑(?)을 하다 **번뜩!!** 아이디어가 떠올랐습니다.

#### 바로 feed를 이용하는 방법이었지요..!!

스팀 API에 Feed만 조회하는 API는 당연히 있습니다.
그러면 이것을 이용하면 위 구현방법중 2번부분 등록한 계정부분을 팔로우로 대처하고, feed 글 리스트 조회 후 3번 부분 특정 태그가 아닌 글은 필터링 하는 방향으로 구현을 하는 것이었습니다.

낮에는 업무시간 중이라 구현을 하진 못하였고, 집에 와서 도전!!! 하였는데!!! 얼추 모양이 나왔습니다.

![](https://cdn.steemitimages.com/DQmaWAGZymDbm8CAPY1xXLopE3T3kCBXyfWrjSHEixpCgLs/image.png)
(위 캡쳐 화면의 글 리스트는 Sample 데이터 입니다.)

주소창에는 임시로 제 부계정 @mamacoco가 들어 있긴 하지만 여기는 운영진에서 새로 만들 계정을 쓰면 될테고, 추천유저들을 팔로우 처리 하면 되는 부분이지요.

현재 니트로스 구조에서는 최선의 방법이라는 생각이 듭니다.

일단 테스트를 좀더 해 봐야겠지만, 큰 문제 없으면 얼른 적용해 보도록 하겠습니다..!!

#### 감사합니다!!