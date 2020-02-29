---
title: '[DEV, JS 웹서비스 트랜드] SVELTE + GraphQL을 이용하여 웹서비스 개발하기 - 1'
tags:
  - sct
  - sct-kr
  - sct-dev
  - s
  - union
  - mini
  - zzan
  - dblog
  - palnet
  - kr-dev
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://cdn.steemitimages.com/DQmTrDZQc777cBrg9Vf5GyoTh1kohNAAymUpUcKj9mYhGWz/image.png\" />\r\n    안녕하세요 햅뽀이입니다.    제가 웹서비스를 개발하고자 하는데 사용할 기술들의 현재 위치가 어느정도 인지 보도록 하겠습니다. 여기에 사용된 자료는 모두 [노마더 코드의 유튜브]( 발췌하였습니다. 언제봐도 친절해 보이는 우리 노마더코드 니꼴라스 형님의 유튜브 매우 추천드려봅니다...!!    ___    ##### 프론트엔드 프레임워크의 관심도를 나....."
date: 2020-02-01 21:40:30
---

![](https://cdn.steemitimages.com/DQmTrDZQc777cBrg9Vf5GyoTh1kohNAAymUpUcKj9mYhGWz/image.png)

안녕하세요 햅뽀이입니다.

제가 웹서비스를 개발하고자 하는데 사용할 기술들의 현재 위치가 어느정도 인지 보도록 하겠습니다. 여기에 사용된 자료는 모두 [노마더 코드의 유튜브](https://www.youtube.com/watch?v=YPMARa8Ex58&t=449s)에서 발췌하였습니다. 언제봐도 친절해 보이는 우리 노마더코드 니꼴라스 형님의 유튜브 매우 추천드려봅니다...!!

___

##### 프론트엔드 프레임워크의 관심도를 나타내는 그래프입니다.
- 제일 우측 그래프(svelte)로 설명을 해보겠습니다.
- 제일 상단 빗살무늬(24.7％) : 이 기술을 처음들어 보았다는 사람의 비율
- 옅은 청록색(22.6％) : 기술을 들어는 보았다.
- 짙은 청록색(44.9％) : 기술을 알고 있고 배우고 싶다.
- Angular 차트의 35.8％를 차지하는 저 붉은색 부분 : 써보긴 했으나 다음번에는 안쓸 것 같다.
- 최하단 짙은 붉은색(6.8％) : 이미 써본 기술이고 다음에도 또 쓰고 싶다는 비율

- 현재 React가 가장 유명하고 많은 사람이 써보았으며, 다음 프로젝트에도 써보길 원하고 있습니다.
- 두번째로 Vue.js도 써본사람은 다음번에도 쓰겠다는 비율이 꽤나 높습니다. 그리고 배우고 싶어 하는 비율도 높습니다.
- 반면에 Angular을 써본사람은 꽤나 있으나 다시 쓰지 않겠다는 비율이 무려 35.8％나 됩니다.
- 제가 선택한 Svelte는 써본사람은 적으나 써본사람의 대부분은 다시 쓴다고 선택하였고, 배우고 싶어 하는 사람들의 비율도 매우 높은편입니다.
![](https://cdn.steemitimages.com/DQmY1jmyyWxtzWmdNynVz4KnLSQCb8GWfBdVyGBtNBwGaLT/image.png)

##### 연도별 만족도 그래프
- React가 항상 상위를 차지하고 있습니다.
- Vue도 한번은 상위를 차지하였다가 3등으로 떨어졌습니다.
- Svelte는 2019년에 처음 소개되었고 바로 2등으로 랭크가 되었습니다.
![](https://cdn.steemitimages.com/DQmdmiTRKYiWpdz3VbMK39TrYMKiL8r77AuFBrwe89s4sX8/image.png)

##### 연도별 흥미도 그래프
- React가 만족도는 높았으나 관심도는 Vue가 좀더 앞서고 있습니다.
- 하지만 Svelte는 출시되지 마자 흥미도에서 1등을 차지하였습니다.
![](https://cdn.steemitimages.com/DQmdtM4mkAWJXLzAWtaE4isNZuhRkBU8esyF1rkd7UJTPkg/image.png)

##### 연도별 인지도 그래프
- 역시나 React가 킹왕짱입니다.
- Angular이 2등을 차지하였고, Vue도 항상 상위를 차지합니다.
- 1, 2, 3등 모두 100％로라서 거의 차이가 없다고 봐도 무방하긴 합니다.
- Svelte는 아직 인지도면에서는 많이 부족함이 보입니다. 2021년 조사에서는 꽤나 비상하기를 바래봅니다.
![](https://cdn.steemitimages.com/DQmPqpEqjcikrVwBU35kKf73MhexorZni9C2bmWaHkfkbko/image.png)

##### 데이터 계층에서의 그래프
- Redux는 React의 라이브러리 답게 많은 유저가 사용을 하였습니다. 하지만 재사용 비율은 꽤나 낮은 편입니다.
- 반면에 Apollo와 GraphQL은 사용해본 유저들의 재사용율이 꽤나 높고, 배우고 싶어 하는 비율도 월등한 것을 확인 할 수 있습니다.
![](https://cdn.steemitimages.com/DQmZ7L29wYkr4pve7VfAokpjsm94AEQtMDkg2nbv3p9Ms5Y/image.png)

##### 데이터 계층 만족도 부분 그래프
- GraphQL, Apollo가 수치상으로 최상위를 점하고 있습니다
- 가장 유명하지만 Redux, Mobx 등이 수치상으로는 꽤나 동떨어져 있습니다.
![](https://cdn.steemitimages.com/DQmWzHKoyhxLzj4q8tkrn7g1faNDRcLowDeM8XEPuEXT7UD/image.png)

##### 데이터 계층 흥미도 그래프
- 위와 마찬가지로 역시나 GraphQL가 최상위를 점하고 있습니다.
- 앞으로도 잘 나갈 기술이라고 보여집니다.
![](https://cdn.steemitimages.com/DQmXTFoF3DtbfGxtJq77tZCfLAhcLbdsizAdMipD2M23LFy/image.png)

##### 데이터 계층 인식도 그래프
- 그래도 역시나 지금까지 잘나가던 Redux가 굳건한 1등을 보여주네요. 하지만 GraphQL도 수치상으론 동일!! 내년에는 따라잡을 수도 있을 것 같습니다.
![](https://cdn.steemitimages.com/DQmQJqpHLw5jtL9q38WhyrWdzuEiPLHcJ2TsEU27AsvbNSk/image.png)

___

저는 위의 이러한 차트를 기준으로 이번 웹서비스에 사용할 기술들을 선택해 보았습니다.
혹시 관심 있는 분야가 있으신지요? 몰랐던 기술들이 있으신지요?(저도 모르는건 많습니다.!!! 너무!!)

개발자 여러분들은 이번기회에 한번 관심을 가져보시는것이 어떠실지? 한번 추천드려봅니다.!!

주말잘 보내세요~~ ^^