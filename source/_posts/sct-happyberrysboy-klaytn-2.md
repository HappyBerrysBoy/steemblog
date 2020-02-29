---
title: '[Klaytn, 클레이튼][2편] 클레이튼에 대해서 알아보자'
tags:
  - sct
  - jjm
  - zzan
  - liv
  - kr-dev
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg  안녕하세요, 햅뽀이입니다.  어제에 이어 오늘도 클레이튼에 대해서 알아보는 시간을 가져봅니다.   1편에서는 클레이튼의 ....."
date: 2019-07-07 12:48:57
---

https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg

안녕하세요, 햅뽀이입니다.

어제에 이어 오늘도 클레이튼에 대해서 알아보는 시간을 가져봅니다. 

1편에서는 클레이튼의 확장성(Scalability), 완료성(Finality), 합의(Consensus), 이스탄불 비잔티움 결함 허용(IBFT) 까지 알아보았습니다.

이번에는 블럭생성 및 전파, 네트워크 구조 까지 알아보겠습니다.

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

## 1. 블럭생성 및 전파
- 클레이튼의 블럭생성 사이클는 라운드(Round)라고 명명 합니다.
- 각 라운드는 끝나는 동시에 새로운 라운드가 시작이 됩니다.(연속해서 라운드 시작/종료를 반복합니다.)
- 각 라운드 간격(블록 생성시간)은 대략 1초 정도 됩니다.
- 라운드 시작시 최초 제안노드는 무작위로 **클레이튼 합의노드(Governance Countil)들 중에서 선정됩니다.
- 여기서 잠깐..!! **합의노드(Klaytn Governance Council)이란?
 : Klaytn Governance Council (KGC)은 클레이튼 노드를 운영하고 클레이튼 개발을위한 의사 결정에 참여하는 조직입니다. 클레이튼 네트워크의 실질적인 운영자라고 할 수 있습니다. KGC는 주로 클레이튼에서 초대받은 신뢰할 수있는 아시아 기업으로 이루어져 있습니다. 클레이튼 메인넷 출시 시점은 18 개의 기업으로 시작되며 현재 논의중인 기업이 참여하고 곧 약 30 개로 확장 될 것입니다. 메인넷 이후 네트워크 안전성이 확인되고 컨센서스 알고리즘에 문제가없는 경우, KGC 회원들을 추가로 받아 들일 수도 있습니다.
- 아래 그림에서 동그라미가 각각의 합의노드들 이라고 볼 수 있습니다. 그중에서 파란색 노드가 현재 라운드의 제안자로 선정된 것이라고 보고 나머지 노드는 검증자 노드라고 보시면 됩니다.
- 각각 노드들(제안노드, 검증노드)은 자신이 제안/검증 노드라는 사실을 Public Key를 통해 입증가능한 암호증명 방법으로 증명합니다. 그래서 서로 문제가 없다는 것이 확인되면 블록 생성단계를 진행합니다.
- 생성된 블럭은 PN을 통해 최종 EN에 까지 블럭이 전파됩니다.(PN, EN은 아래에서 설명)

![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/USKEqfdF-image.png)

## 2. 네트워크 구조
- 아래 그림과 같이 클레이튼 네트워크는 크게 CNN/PNN/ENN 세개의 그룹으로 이루어집니다.

- CNN(Consensus Node Network)은 블록생성/검증을 위한 노드들의 집합입니다. CNN에서는 외부 네트워크망과 연동되지 않습니다. 적은 수의 노드들만 존재 하기 때문에 성능 향상을 가져 올 수 있습니다.
- PNN(Proxy Node Network)은 CNN으로 부터 검증된 블럭을 전달받아 ENN으로 블럭데이터를 전송하는 역할을 합니다. PNN은 ENN에 블럭 전송의 기능만 맡기 때문에 수십 수백대의 ENN과 연동이 가능합니다.
- ENN(Endpoint Node Network)은 최종 단위의 노드로써 PNN으로 부터 블럭 정보를 받아 최종 Client와 연동되는 노드들의 집합입니다. ENN은 블럭생성/전파에는 전혀 관여할 수 없습니다. ENN의 참여조건은 없기 때문에 누구나 구성할 수 있습니다. 
- Core Cell : 하나의 CNN과 이와 연동된 여러개의 PNN으로 이루어져 있고, 이 하나의 Set이 Governance Council 하나라고 보시면 됩니다. Core Cell에 참여하기위해서는 신뢰할 수 있는 기업급이 되어야합니다. 
- CN/PN/EN Bootnode : 각각의 네트워크망 안에는 Bootnode가 존재합니다. 각각 부트노드는 각각의 네트워크망 안에서 새로운 Node가 생기거나 사라지는 경우 이를 관리하는 노드이며, 클레이튼에서 직접 관리하고 있습니다.
- 블록체인 외부에서 서비스를 할 경우 EN과 서로 통신하며 서비스를 하면 됩니다.

![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/HK0197US-image.png)




![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)

클레이튼은 대체로 합리적인 방식을 채택한 것 같습니다. 성능과 확장성을 동시에 잡을 수 있는 방향으로 말이지요. CN을 신뢰할 수 있을만한 기업을 참여시킴으로써 네트워크 사용자에게 신뢰감을 올려 주며 많은 수의 노드로 운영되지 않기 때문에 성능을 극대화 할 수 있습니다. 

거기에 각각 최소한의 PN을 두어 실제 최종 서비스에 운영되는 EN에 블록정보 전파를 전담 시키는 구조로 만들었습니다. PN은 블럭 전파의 업무를 전담하여 수많은 EN과 통신이 가능하도록 말이죠. 만약에 시스템 유저가 더 늘어나서 더 확장성이 필요하면, PN의 수를 더 늘려서 추가로 수많은 EN을 관리 할 수 있도록 됩니다.

오늘은 여기까지 정리하도록 하겠습니다. 
읽어주셔서 대단히 감사합니다..!!

#### 지난 글
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 1편](https://steemit.com/sct/@happyberrysboy/klaytn-1)

![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)