---
title: '[happy service update] 주사위 기능 보완 및 Steemservice 계정 추가'
tags:
  - sct
  - sct-kr
  - sct-freeboard
  - aaa
  - zzan
  - liv
  - jjm
  - union
  - palnet
  - happy-dice
author: happyberrysboy
categories: game
excerpt: "<img src=\"https://steemitimages.com/0x0/https:/\" />\r\n/cdn.steemitimages.com/DQmeVyCnkva2SjkjT5mk9XPo2BJzbK7szFE1pDqqAHrSBsC/WHALE_TITLE_COLORED_LOW.jpg)  안녕하세요, 햅뽀이입니다.  아까.. 2시에 자려고 했었는데 갑자기 또 주사위 수정하고 싶은게 생겨서.. 수정하고 나니 3시가 넘었군요!! ㅠㅠ 오늘은 일찍 자려 했는데 말이죠......"
date: 2019-09-11 03:19:30
---

![](https://steemitimages.com/0x0/https://cdn.steemitimages.com/DQmeVyCnkva2SjkjT5mk9XPo2BJzbK7szFE1pDqqAHrSBsC/WHALE_TITLE_COLORED_LOW.jpg)

안녕하세요, 햅뽀이입니다.

아까.. 2시에 자려고 했었는데 갑자기 또 주사위 수정하고 싶은게 생겨서.. 수정하고 나니 3시가 넘었군요!! ㅠㅠ
오늘은 일찍 자려 했는데 말이죠.. 이미 실패를 해버렸습니다. ㅎㅎ

간단히 수정사항 포스팅하고 가봅니다.

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

### steemservice 계정 추가
- 이제는 happy-dice, happy-pick 호출 시에 제 본계정(happyberrysboy)가 아닌 **steemservice** 라는 계정에서 댓글을 달아줍니다.
- 진작에 바꾸었어야 할 부분이었는데, 이러다 저러다 보니 이제서야 수정을 하게 됐네요.
- 덕분에 제가 단 댓글 리스트는 주사위 숫자로 모두 덮혀버렸습니다. ㅠㅠ
- 안그래도 요즘 소통도 부족했는데, 엉망이 된 리스트 때문에 더 관리도 힘들어 졌습니다.
- 아무튼 이제는 steemservice 잘 봐주세요!! ^^

### happy-dice 본문 작성시 댓글 안달림(happy-pick는 본문에 작성해도 작동합니다.)
- 본문에 dice 명령어 가르쳐 주는 내용이 들어가는데, 거기서 다이스가 호출되는 경우가 종종 생겼습니다.
- 사용법에서 어긋나는 경우도 있다보니 주로 에러를 뱉어 내곤 했었지요.
- 그래서 본문에서는 호출해도 응답하지 않도록 수정하였습니다.

### happy-dice/happy-pick 본문 내용 수정시 추가로 작동(주사위 또는 pick) 하는 부분 수정
- 이제 더이상은 코멘트 내용을 수정해도, 추가로 주사위를 굴리지 않습니다.(추가로 happy-pick가 작동하지 않습니다.)
- 최초만 댓글이 작성되고, 내용이 수정되어도 추가로 결과 댓글이 달리지 않습니다.

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

이상입니다!!!

#### 모든 분들 평안한 밤 되시기 바랍니다!! ^^

___
마지막 테스트 한번더!!!
댓글에 dice야 달리지 마라!! 얍!!!
#happy-dice