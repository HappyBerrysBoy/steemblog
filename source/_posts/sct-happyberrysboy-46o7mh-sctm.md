---
title: SCTM 소각용 재매입 방안 계산식 공유
tags:
  - sct
  - sct-kr
  - sct-notice
  - union
  - liv
  - palnet
  - zzan
author: happyberrysboy
categories: life
excerpt: "<img src=\"https://cdn.steemitimages.com/DQmTGJwNikedQKjNJ2ogTn2xiyTjYRE3gp5a88NrWTrjM53/image.png\" />\r\n안녕하세요, 햅뽀이입니다.  어제 SCTM 소각을 위한 재매입 방법에 대해서 채팅방에서 많은 대화가 오갔습니다.  홀더분의 의견을 적극 수용하고, 운영진 내부회의 결과 괜찮은 방안이라 생각하여, 해당 방식으로 확정하고 진행할 예정입니다.  의견은 @tradingideas 님이 내어 주신 것이구요. 어느정도 예측이 가능하면서도, 가격이 유동적인 적절한 방안을....."
date: 2019-10-19 10:48:51
---

안녕하세요, 햅뽀이입니다.

어제 SCTM 소각을 위한 재매입 방법에 대해서 채팅방에서 많은 대화가 오갔습니다. 
홀더분의 의견을 적극 수용하고, 운영진 내부회의 결과 괜찮은 방안이라 생각하여, 해당 방식으로 확정하고 진행할 예정입니다.

의견은 @tradingideas 님이 내어 주신 것이구요. 어느정도 예측이 가능하면서도, 가격이 유동적인 적절한 방안을 마련해 주셨습니다. 표에서는 간단히 보여주신 부분이지만, 실제로 계산되는 부분은 조금 복잡한 부분이 있어서, 이 포스팅을 통해서 자세히 설명 드리려고 합니다.

___

### 전체적인 작업 흐름도
1. @sct.min 계정의 큐레 수익(SCT)를 KRWP로 전환하여 20％는 소각하고 나머지는 @sctm.burn 계정으로 전송한다.
2. 현재 호가를 확인 하고 KRWP와 SCTM 교환을 원하는 홀더가 있는 경우 SCTM을 @sctm.burn 계정으로 보낸다.
3. @sctm.burn 계정은 매일 9시 30분에 하루동안 모인 SCTM수량을 보고 현재 호가에 맞추어 KRWP를 분배한다.
4. 현재 보유중인 KRWP가 하루동안 모인 SCTM수량만큼 충분히 분배가 ***가능한 경우***, 모두 분배하고, 다음날 호가를 10％ ***상승***시킨다.
5. 현재 보유중인 KRWP가 하루동안 모인 SCTM수량만큼 분배가 되지 ***못하는 경우***, 분배할 수 있는 만큼만 분배후, 남은 SCTM은 참여자들에게 다시 돌려준다. 그리고 다음날 호가는 10％ ***하락***시킨다.

### 실제 계산 식

##### 클레임 및 KRWP 전환
- 노란색 부분은 일별로 변동이 가능한 부분이다.
- 변환된 KRWP : 클레임 된 SCT 수량 X 스팀가격 X SCT가격 / 1000
- 소각후 KRWP : 변환된 KRWP X 0.8(80％)
- 총 KRWP 보유량 : 어제 남은 KRWP + 오늘 소각후 KRWP
- KRWP의 원화 가치 : 총 KRWP 보유량 X 1000
![](https://cdn.steemitimages.com/DQmTGJwNikedQKjNJ2ogTn2xiyTjYRE3gp5a88NrWTrjM53/image.png)
<br><br>
##### 호가 계산 및 참여된 SCTM 가치 계산
- 제일 첫날 첫 호가는 6Steem으로 계산한다.
- 호가(Steem) : 전날 KRWP가 남았을 경우 전날 호가 + 10％, 전날 KRWP가 모두 소진된 경우 전날 호가 - 10％
- 호가 원화가치 : 호가 * 스팀가격
- SCTM 참여량 : SCTM과 KRWP 전환을 원하는 유저들이 보낸 총 SCTM의 양
- 참여된 SCTM의 원화가치 : 호가 원화가치 * SCTM 참여량
![](https://cdn.steemitimages.com/DQmYBkBkVHjNYEnrw4Bkv9yfpveLQgpa3BdAknoJyQHMxF5/image.png)
<br><br>
##### 분배 방법 및 비고
- KRWP 분배량(KRWP의 원화가치 - 참여된 SCTM의 원화가치 > 0 경우)
   : 총 KRWP 보유량 - (KRWP의 원화가치 - 참여된 SCTM의 원화가치) / 1000
- KRWP 분배량(KRWP의 원화가치 - 참여된 SCTM의 원화가치 <= 0 경우)
   : 총 KRWP 보유량
- 남은 KRWP : 총 KRWP 보유량 - KRWP 분배량
- 남은 SCTM : KRWP의 원화가치 - 참여된 SCTM의 원화가치 <= 0 경우 모든 KRWP를 분배하고 남는 수량
- 남은 SCTM이 있는 경우 비율에 따라서 모두 반환
- 비고 : 당일 KRWP를 분배후 남은 KRWP가 있는 경우 다음날 호가 10％ 상승, 아닌 경우 10％ 하락
![](https://cdn.steemitimages.com/DQmUsg9ua4tuiAMQzZnL1118DrfhJYSFqm2eHVEHTPcRQab/image.png)



___

쓰고보니 여전히 복잡하네요. ㅠㅠ 죄송합니다. 설명능력이 부족한가봅니다.
더 자세히 쓰려고 했지만, 일단 개발이 좀더 시급한 것 같아, 추후 기회가 되면 부가 설명을 해보도록 하겠습니다.

주말의 시작이네요!! 다들 즐겁고 즐겁고 또 즐거운 주말 보내시길 바랍니다.

감사합니다.