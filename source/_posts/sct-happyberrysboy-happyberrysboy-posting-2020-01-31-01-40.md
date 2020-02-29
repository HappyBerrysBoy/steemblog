---
title: '[DEV] SVELTE + GraphQL을 이용하여 웹서비스 개발하기 - 0'
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
excerpt: "<img src=\"https://cdn.steemitimages.com/DQmTrDZQc777cBrg9Vf5GyoTh1kohNAAymUpUcKj9mYhGWz/image.png\" />\r\n    안녕하세요 햅뽀이입니다.    오늘 새롭게 알게된 웹프레임워크가 있습니다. Svelte 라는 것인데, 현재 3대장인 React, Vue, Angular의 아성에 도전하는 프로젝트입니다. 사용법이 위 3대장중 가장 쉽다는 Vue 보다도 간결하고 이해가 쉽고 직관적인걸로 보여서 Svelte를 이용해서 한번 웹서비스를 만들어 볼까 합니다.    그리고 서....."
date: 2020-01-31 20:40:30
---

![](https://cdn.steemitimages.com/DQmTrDZQc777cBrg9Vf5GyoTh1kohNAAymUpUcKj9mYhGWz/image.png)

안녕하세요 햅뽀이입니다.

오늘 새롭게 알게된 웹프레임워크가 있습니다. Svelte 라는 것인데, 현재 3대장인 React, Vue, Angular의 아성에 도전하는 프로젝트입니다. 사용법이 위 3대장중 가장 쉽다는 Vue 보다도 간결하고 이해가 쉽고 직관적인걸로 보여서 Svelte를 이용해서 한번 웹서비스를 만들어 볼까 합니다.

그리고 서버단은 요즘 한창 핫하다는 GraphQL을 이용해볼 예정이구요. 

마지막으로 UI Component는 Semantic-UI를 이용해볼 예정입니다.

Semantic을 제외한 위 두가지 모두 저에겐 익숙한 프레임워크는 아니다보니 다소 시간이 걸릴 수는 있겠지만, 새롭게 배우고 싶은 부분이기도해서 한번 도전해보려고합니다.



___

먼저 처음에는 간단히 저도 학습하는 내용들을 추가해보면서 진행해 나갈까 합니다. Svelte에 대한부분 GraphQL에 대한 부분들을 다루면서 천천히 웹 서비스를 개발해 나가도록 해보겠습니다.

2월 부터 영어 포스팅도 시작해야하는데!!! 빡센 한해가 되겠군요..!! 다 성공했으면 하는 바램이 있습니다.

___

### 간단한 Svelte 소개


![](https://cdn.steemitimages.com/DQmNyZdUyqzewdbgddkGHvCQrcEAU9ATqFKLvCerbUCkcY5/image.png)
- 코드가 간결합니다. 아래 다른 이미지에서 보시면 아실겁니다.
- 가상 DOM은 React, Vue에서는 장점으로 소개되었지만, Svelte에서는 거기에 불필요한 자원 소모는 필요 없다고 주장하기도 합니다.
- 복잡한 라이브러리를 사용하지 않고 순수 Javascript만으로 반응형을 구현하였습니다.

### React/Vue vs Svelte
- React의 소스(상단)와 Vue의 소스(하단)의 코드양에 비해 Svelte(최하단)의 코드량이 매우 짧은 것을 확인 할 수 있습니다.
![](https://cdn.steemitimages.com/DQmNgyxqAKtSoBcR4RrvvMv8FyoLt5t5PtwrFpYqXoNvAwL/image.png)

![](https://cdn.steemitimages.com/DQmaaqXGG7YjSXbTYcP7GsYTF7PDoeJdr9HZCPvcAXZawhN/image.png)

___

저는 Svelte를 처음 접하면서 가장 마지막에 예시로 보여줬던 소스를 보고 너무 직관적이고 좋아서 사용해보려고 하고 있습니다. 기존 React, Vue에 비해서 자료가 많지 않을 것 같아서 조금 걱정이긴 하지만, 천천히 진행해보려고 합니다.


### Svelte 가즈앙!!