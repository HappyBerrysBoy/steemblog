---
title: '[kr-dev] Steemit Tools 유저 바로가기 기능 구현'
tags:
  - kr-dev
  - busy
  - mini
  - jjm
  - kr
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://ipfs.busy.org/ipfs/Qman2EX2PHQ4YpS5QRttNh6yBApcQQVc3YD2iheeThsdS8\" />\r\n  안녕하세요, 해피베리보이입니다.  요즘 스팀 관련 이런 저런 글들이 많은데요...... 라고 시작하는 분들이 많으셔서 한번 따라해봤습니다. 저는 그냥 코딩 글 쓸겁니다.. ㅋㅋ 관심이야 물론 많지만.. 음.. 저는 글쓰기 능력이 아직 좀 부족해서 그런지.. 처음에 쓰려고 했던말이 나중으로 갈수록 자꾸 다른 주제로 빠지더라고요 ㅠㅠ 그럴수록 더 연습해야하....."
date: 2019-05-11 21:55:30
---

![](https://ipfs.busy.org/ipfs/Qman2EX2PHQ4YpS5QRttNh6yBApcQQVc3YD2iheeThsdS8)

안녕하세요, 해피베리보이입니다.

요즘 스팀 관련 이런 저런 글들이 많은데요...... 라고 시작하는 분들이 많으셔서 한번 따라해봤습니다.
저는 그냥 코딩 글 쓸겁니다.. ㅋㅋ
관심이야 물론 많지만.. 음.. 저는 글쓰기 능력이 아직 좀 부족해서 그런지.. 처음에 쓰려고 했던말이 나중으로 갈수록 자꾸 다른 주제로 빠지더라고요 ㅠㅠ 그럴수록 더 연습해야하지만.. 저는 코딩을 더 연습해야 합니다..  

Steemit Tools가 조금더 개발이 되었습니다.
오늘 소개드릴 기능은

#### 유저정보확인/바로가기 기능입니다.
- 저도 스팀잇 유저이기 때문에 Steemit.com 사이트를 쓰면서 불편한 점은 많지요.
- 가끔 아.. 이 유저분 어떻게 사시나? 궁금해서 찾아 볼일이 있는데 그나마 개발자인 저는 주소창에 account를 입력해서 찾아가는 식으로 가곤 했었습니다.
- 생각보다는 번거로운 일이지요. 그래서 바로가기 기능을 추가 했고요.
- 그리고 간단한 유저 정보도 바로 볼 수 있도록 하였습니다. 아직은 사진만 딸랑 나오지만, 점차적으로 추가해 나갈 예정입니다.

![steemittool2.gif](https://cdn.steemitimages.com/DQmZs44FZ9ARKGVbrWheJuRz6SAGsrfqmMvfiys3nJjhh2a/steemittool2.gif)

- 맥북에서 gif 저장하는 툴 중에 GIPHY CAPTURE를 사용하는데, 용량이 너무 크게 저장이 되네요 ㅠㅠ
- 용량 때문에 작게 저장했더니 이따구로... 나중에 캡쳐된 화면으로 부가 설명 드리겠습니다.

##### 기능 화면
- 지난 포스팅에서도 보여드렸는데, 메뉴화면이고, 첫번째 버튼이 유저정보/바로가기 기능입니다.
(이건 또 왜이렇게 크게 나오냐..)
![image.png](https://ipfs.busy.org/ipfs/QmeKBxBnPYGcMGmi5rDRTsN7894FLw95aaLMhj6wzbvRLR)

- 클릭 시 아래 그림처럼 우측에 화면이 나타납니다.(버튼들 거리 배열은 살짝 손봐야 해요.. 일단 기능 위주로!!)
- Add : 유저를 추가 할 수 있습니다.
-  i 아이콘 : 유저 정보를 볼 수 있습니다.
- 화살표 아이콘 : 유저페이지로 바로 이동합니다.(Sample : https://steemit.com/@happyberrysboy)
- 휴지통 아이콘 : 등록된 유저를 삭제합니다.
![image.png](https://ipfs.busy.org/ipfs/QmW8WVoCVADFaFndRDpZK7o91F5ww5dZYkLtuQEQHUAxUd)

##### Add 기능
- 클릭 시 유저명을 입력하는 화면이 나타나고, 유저명을 입력 후 Add를 누르면 아래 그림처럼 추가가 됩니다.
![image.png](https://ipfs.busy.org/ipfs/QmdD1pVLmVe9vvpYcMcFsw7AHL6drZrsVDRbJjZjZ3nZ1P)

![image.png](https://ipfs.busy.org/ipfs/QmT1179A4RCKni7cuyDZx8oU5QL6aaB2TaVr9J9jgk65Xa)

##### 유저 정보 기능
- i모양 아이콘을 클릭하면 유저 정보가 나옵니다.
- 아직은 이미지만 딸랑 있지만, 나중에 간단한 유저정보들은 다 입력해 볼 생각입니다.

![image.png](https://ipfs.busy.org/ipfs/QmUJ55PH4scHJAeYiMH5X5yjPNECZkW6bXh6zcqvUd1Kfk)

##### 바로가기 기능
- 유저 페이지로 바로 이동합니다.
![image.png](https://ipfs.busy.org/ipfs/QmeNaHFLZKTUVWurfU4Q8tzEei2q1JQrwfuPGoFMxCHAGC)

##### 앞으로 추가가 될 수도 있는 기능들(장담을 못해서.. ㅠㅠ)
- 일단 하고 싶은건 모조리 정리하였습니다.
- 간단히 개발되는거 부터 추가하고 배포하도록 해볼게요..!!
- 추가로 원하시는 기능 있으면 언제든지 댓글에 남겨주십시오.(개발 여부는 보장 못하지만요!!)

![image.png](https://ipfs.busy.org/ipfs/Qmdza4mdKBHeC4iBfCbKveuwGFVgphjeoqsaoAH1wrVk7g)

___

토요일이 지나가려합니다!!! 남은 일요일!! 매우 즐겁게 보내시길 바래봅니다!!
