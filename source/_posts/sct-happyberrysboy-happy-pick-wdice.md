---
title: happy-pick 추첨기능 한번 이용해보세요.(wdice와 유사한 기능입니다.)
tags:
  - sct
  - aaa
  - zzan
  - jjm
  - happy-pick
  - freeboard
  - kr-dev
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)  안녕하세요, 햅뽀이입니다.  며칠 동안 happy-pick 기능을 테스트하다보니 보신분들도 계실 것 같기도? 말기도? ....."
date: 2019-07-14 08:36:15
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)

안녕하세요, 햅뽀이입니다.

며칠 동안 happy-pick 기능을 테스트하다보니 보신분들도 계실 것 같기도? 말기도? 한데요. 가끔 이벤트로 추첨같은 걸 이용하실 때 활용 하실 수 있는 기능을 하나 만들어 보았습니다. 최근에 스팀서버 모니터링이 필요해서 만들고 있었는데, 마침 @ukk님이 이런 기능 개발이 가능하냐고 하셔서 만들게 되었습니다.

서비스 이름은 **happy-pick**로 명명했어요. 뭔가 주로 좋은 이벤트에 활용되는 경우가 많을 것!! 같아서요. 당첨되면 happy해질 수도 있고, 제 아이디에 happy도 있고 해서 **happy-pick**으로 정해보았습니다.

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

# 사용법
- #happy-pick 사용법에 대해서 알려드리겠습니다.
- 보기를 보시면서 설명 드리겠습니다. 명령어는 총 3부분으로 나뉘어 집니다.

```
        호출명령어    추첨인원       추첨대상:가중치
      ___________   _____   ____________________
보기 : #happy-pick     2     (a:1, b:2, c:3, d:4)
```
- 호출명령어는 #happy-pick 을 사용하시면 됩니다.
- 추첨인원은 추첨대상에서 총 몇명을 뽑을 것인지 써주시면 됩니다.(생략하셔도 됩니다. 그럴 경우 1명만 뽑게 됩니다.)
- 추첨대상:가중치는 추첨에 포함될 후보군들입니다. 후보군들 뒤에 콜론(:) 뒤에 가중치를 입력하실 수 있습니다. 가중치를 생략하는 것도 가능한데, 그럴 경우 자동으로 1로 설정됩니다.
- 사용 가능 범위(포스팅 + 댓글 + 대댓글 모든 곳에서 호출 가능합니다. **단, 한포스팅, 한댓글에 여러번 호출시 가장 상단의 하나만 작동하게 됩니다.)
- 실제 호출예시 및 결과 댓글 모양
![](https://cdn.steemitimages.com/DQmYLgm23QKtgcHtgZ2GMWM84nNirrEa9aG54T2bcZnG25T/image.png)

# 다양한 예시
- 짧고 단순하게 쓴 경우(가중치는 모두 1)
```#happy-pick (짜장, 짬뽕, 볶음밥, 잡채밥)```
- 여러개를 추첨해야 할 경우(가중치는 모두 1)
```#happy-pick 2 (SCT, AAA, ZZAN, STEEM, SBD, LEO)```
- 가중치를 주고 1명만 뽑는 경우
```#happy-pick (짜장:50, 짬뽕:20, 볶음밥:30)```
- 가중치도 주고 여러개를 뽑는 경우
```#happy-pick 3 (lucky2:5, zzing:10, anpigon:15, wonsama:20)```


# 소소한 이벤트
- 본 포스팅의 댓글에 #happy-pick를 호출 해주시는 분들께 1스팀씩 드리도록 하겠습니다.(소소하게^^;;)
- 명령어를 뭔가 웃기거나, 획기적으로(제가 생각지 못했던 내용) 사용해주셨다고 판단되는(주관적으로) 분께는 3~10스팀씩 드리도록 하겠습니다.
- 아래 @jinuking 님처럼... ㅎㅎ happy-pick가 왜 저런 결과를.. ㅠㅠ @jinuking 님에게는 5스팀을 드리도록 하겠습니다.(추첨 운도 좀 따른듯?)
![](https://cdn.steemitimages.com/DQmVHqqkMptStg7jKA3mUXuqoWxbjpkQTXprJQwQmgon22W/image.png)
- 이벤트 기간은 7월 16일(화) 밤 23:59 까지 하도록 하겠습니다.
- 많은 이용 부탁드립니다.

# 아이디어 모집
- 추가로 이렇게 작동하면 더 좋겠다!! 라고 생각되시는 내용이 있으시면 알려주십시오.
- 너무 복잡하지 않은 범위내에서는 충분히 기능추가가 가능할 것 같습니다.
- 기능 추천 해주시는 분들께는 추가 스팀을 선물로 드리겠습니다.(스팀이 모자를시 SCT, AAA 등 가능!!)

# 경고!!
- 아직 제가 모니터링을 돌린지가 얼마 되지 않아, 다양한 예외사항 처리가 부족합니다.
- 가끔 #happy-pick 댓글이 늦게 달리는 경우 문제가 있구나... 생각해주시면 됩니다. ㅠㅠ
- 그래도 문제가 된 부분에서 멈추고, 다시 가동시키면 언젠가는 다시 댓글이 달릴테니 기다려주시면됩니다.(하루던 이틀이던..??)

## 여기까지 읽어주셔서 감사합니다.