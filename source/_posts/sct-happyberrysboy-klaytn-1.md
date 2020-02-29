---
title: '[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자. 1편.'
tags:
  - sct
  - jjm
  - zzan
  - liv
  - kr-dev
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)  안녕하세요, 햅뽀이입니다.  지난번 포스팅에서도 말씀드렸듯이 클레이튼 스터디를 시작하였습니다. 동영상 강의를 보면서 정....."
date: 2019-07-06 12:47:24
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)

안녕하세요, 햅뽀이입니다.

지난번 포스팅에서도 말씀드렸듯이 클레이튼 스터디를 시작하였습니다. 동영상 강의를 보면서 정리한 내용을 시리즈 물로하여 포스팅으로 전달해 드리도록 하겠습니다. 

자 그럼 시작해볼까요?

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

# 0. 클레이튼(Klaytn) 이란?
- 카카오에서 만들고 있는 블록체인으로서 강력한 보안성 및 투명성을 제공하면서 엔터프라이즈급 성능 및 안전성을 제공하는 **퍼블릭 블록체인을 지향** 합니다

# 1. Klaytn의 Scalability(확장성)
- Scalability를 측정 할때는 주로 TPS(Transaction per Second), Block Interval 로 측정합니다.
- Visa의 TPS는 대략 1700 TPS 수준
- 비트코인 : Block Interval 10분,  대략 7 TPS
- 이더리움 : Block Interval 대략 15초, 15 ~ 20 TPS
- **클레이튼 : Block Interval 대략 1초,  3000 TPS**

# 2. Finality(완료성)
- 블록에 담긴 거래가 바뀔 수 없다는 걸 보증할 수 있는 단계를 말합니다. 
- 이말은 곧 확실히 믿을 수 있는 거래로 확인되는데 까지 걸리는 시간을 말합니다.
- 비트코인의 Finality 까지 걸리는 시간 : 60분(6번 검증)
- 이더리움의 Finality 까지 걸리는 시간 : 6분(25번 검증)
- **클레이튼의 Finality 까지 걸리는 시간 : 1초!!!!** : 합의와 동시에 바뀔 수 없도록 바로 완료처리를 해버립니다.

# 3. Consensus(합의)
- Public 블록체인 : PoW, PoS 등
- Private 블록체인 : pBFT, Raft 등을 사용
- Private 블록체인에서 사용하는 BFT(비잔티움 결함 허용)은 참여 노드수를 제한하여 성능을 높이는 특징을 가집니다.
- 클레이튼은 IBFT(이스탄불 비잔티움 결함 허용)을 합의 알고리즘으로 적용하였습니다.
- 이 알고리즘으로 강력한 보안성 및 투명성을 제공하면서 엔터프라이즈급 성능 및 안전성을 제공할 수 있습니다.
- 이 부분이 가능한 이유는 성능 향상을 위해서 BFT를 적용함과 동시에 생성된 블록을 누구나 검증 할 수 있도록 공개를 하여 신뢰성을 확보 하도록 하였기 때문입니다.

# 4. IBFT(이스탄불 비잔티움 결함 허용)
- IBFT는 5개의 단계를 가집니다. 
- 라운드마다 하나의 제안(proposer) 노드를 선정합니다. 남은 합의 노드들은 검증노드(Validator)로 됩니다.
- Propose 단계 : 선정된 제안노드가 블럭을 생성합니다. 거래들을 담는 다는 말이죠.
- pre-prepare 단계 : 그리고 제안노드가 생성한 블럭을 다른 검증노드들에게 전파하는 단계입니다.
- prepare 단계 : 검증자 노드들이 제안노드로 부터 블럭을 받으면, 다른 노드들에게 잘 받았다라는 신호를 전파하는 단계입니다. 3번 검증노드의 경우는 현재 작동이 안하는 상태라고 가정하였습니다. 그래서 3번 검증노드는 받기만 하고 전파를 하진 않습니다.
- commit 단계 : 전달받은 블록을 확인해서 체인에 등록해도 될건지 다른 검증노드들과 합의를 하는 단계입니다. 여기서 2/3 이상이 블록체인 등록이 가능하다고 승인을 하면 이상태에서 바로 Finality를 확보하게 됩니다. 바로 변동 불가능한 블록으로 처리를 한다는 말입니다.
- reply 단계 : 이 블록을 체인에 등록하는 단계입니다.
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/nB5ahhN4-image.png)

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

클레이튼을 공부하면서 드는 생각은, 비트코인, 이더리움과는 달리 뛰어난 성능을 가지면서 바로 변경 할 수 없는 블록을 만들어 줌으로서 이제 실생활에서 충분히 사용가능한 블록체인이 나타났구나 하는 생각이 들었습니다. 게임 같은 경우 게임사에서 마음대로 조작을 할 수도 없을 테고, 수 많은 조작이 되어야 하지 않아야 하는 부분에서 블록체인이 적용되면 앞으로 사회에 많은 부분이 변경 될 것같다는 생각이 들기도 했고요. 

아직 메인넷이 런칭되지 않은 상태라 좀더 기다려봐야 하겠지만, 정상적으로 잘 작동만 한다면 정말 훌륭한 체인이 될 것 같습니다. 이런 기대감을 가지고 앞으로 더 열심히 공부해 봐야겠습니다!!!

여기까지 읽어 주셔서 대단히 감사합니다.