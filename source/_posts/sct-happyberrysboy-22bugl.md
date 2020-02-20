---
title: 뽑기판 로또참여권 구매 기능 개발
tags:
  - sct
  - sct-kr
  - sct-freeboard
  - s
  - union
  - mini
  - zzan
  - dblog
  - palnet
author: happyberrysboy
date: 2020-02-04 21:10:45
---

안녕하세요 햅뽀이입니다.

오래간만에 오늘 뽑기쪽에 업데이트가 있었습니다. 라운드8부터 로또추첨방식이 바뀌면서 그 뒤로 당첨자가 아직 1명도 나오지 않고 있군요. 그러면서 점차적으로 보상 총액이 잘 쌓이고 있습니다.

![](https://cdn.steemitimages.com/DQmZugUv7cNrZgE1W4yhzqcdtzRvaZraVMmX3VG7HMXUQsH/image.png)

여기에 또 한국인의 숨어 있는 승부사 기질을 끄집어 내기위해서 기능을 추가하였습니다.

바로바로....

### 로또참여권 구매기능!!
- 메뉴는 기존에 뽑기권 구매하는 곳과 같습니다.
![](https://cdn.steemitimages.com/DQmeEyaev1pydFUnjam9xJxrMUUUhaEnMT6A6WzKaMeUKFy/image.png)
- 아래와 같이 로또참여권 구매가 가능해졌습니다.
- 주의사항은 아래 이미지에 나와 있지만, 잘보이지 않기 때문에 다시 알려드립니다.

> 로또참여권의 로또번호는 스팀 트랜잭션 ID를 이용해야하므로 1장씩만 구매가능합니다.
로또참여권의 가격은 현재 모인 총액에 따라 가변적입니다.

![](https://cdn.steemitimages.com/DQmNoog2gLXJokvmL9a4hQuCkjsBZ6vo2fJAvNn2eQVTYHQ/image.png)

- 그렇습니다. 로또참여권은 한번에 하나의 트랜잭션 번호만 추출하므로, 동시에 1장을 초과하여 구매할 수 없습니다.
- 그리고 로또참여권은 로또보상 총액이 변화함에 따라 기회비용이 변하므로, 가격을 가변적으로 구성하였습니다.
- 로또 보상총액이 10000 SCT에 육박하게 되면  아마 15SCT 가량으로 올라가게 될 것입니다.(물론 3등만 되어도 당첨금은 1000 SCT)
- 로또를 뽑기에서 뽑은사람과 구매한 사람의 차이도 나도록 수정하였습니다.

### 로또추첨 메뉴 수정
- 예전에는 이전 라운드의 추첨결과만 보여주었지만, 이제는 현재 라운드에 뽑기권을 뽑은 사람들 리스틀르 보여줍니다.
- 아래에 제 계정명(happyberrysboy)의 옆에 뽑은 숫자 "0"으로 표시된 것은 로또추첨권을 구매한 것을 뜻합니다.(표기 문자는 변경될 수 있습니다.)

![](https://cdn.steemitimages.com/DQmPmrG6G7gGfrrsucy8KEG4FHxPyuGJjRjJsqy8kE1jPXD/image.png)

___

##### 앞으로 Steem으로도 로또추첨권을 구매 할 수 있도록 개발할 예정입니다.
##### 프로그램 배포는 내일 오전 9시 이전에 될 예정입니다.
앞으로 보상이 많이 높아지면, 로또추첨권 구매!! 한번 고려해보십시오.