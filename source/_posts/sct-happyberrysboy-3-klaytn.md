---
title: '[3편][Klaytn, 클레이튼] 클레이튼에 대해서 알아보자'
tags:
  - sct
  - kr-dev
  - jjm
  - zzan
  - liv
  - whan
  - klaytn
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg  안녕하세요, 햅뽀이입니다.  오늘도 클레이튼에 대해서 공부를 해왔습니다..!! 벌써 3탄이군요!! 오늘의 주제는 코어셀,....."
date: 2019-07-08 13:02:15
---

https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg

안녕하세요, 햅뽀이입니다.

오늘도 클레이튼에 대해서 공부를 해왔습니다..!! 벌써 3탄이군요!!
오늘의 주제는 코어셀, 서비스체인입니다.

바로 고고 해보겠습니다.

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)


# 1. 코어셀
- 일반적으로 사용자가 많아져서 확장이 필요한 경우일반적인 중앙화된 서비스는 서버를 늘리고, 들어오는 요청을 분산시킵니다.
- 하지만 클레이튼은 코어셀의 서버 성능을 증가 시키는 방향으로 확장성을 확보합니다.
- 코어셀 숫자 자체를 늘릴 경우 합의하는데 시간이 더 길어지기만 할뿐, 서버 숫자를 늘리는 것은 아무런 도움이 되지 않기 때문이지요.
- 여기서 잠깐!! 코어셀(합의노드)에 참여 할 수 있는 최소 하드웨어 스펙은?
```
- Physical Core가 40개 이상
- 256GB RAM
- 1년치의 데이터를 저장 할 수 있는 14TB 저장
- 10G 네트워크
```

- 자세한 설명을 위해서 다시 지난번에 설명드렸던 코어셀의 이미지를 가져왔습니다.
![](https://cdn.steemitimages.com/DQmYStUrQsrKcqGZNSm292Wv1149CrjGpbg8JUpZ2tn668b/image.png)

- 코어셀은 그림과 같이 1개의 CN(Core node)과 여러개의 PN(Proxy Node)으로 이루어져 있습니다.  이렇게 이루어져 있는 경우 CN은 현재 네트워크의 규모에 맞는 수만큼의 PN 수량만 유지하면 되기 때문에 블록생성에만 집중을 할 수가 있는 구조인 것이지요.

- 위와 비슷한 말이기는 하지만, 만약에 코어셀이 바로 EN(Endpoint Node)과 연결될 경우, 서비스가 확장되어 EN이 더 늘어나면 거기에 응하기 위해서 CN을 늘려야 할 수 밖에 없고, CN이 늘어나면 늘어 날 수록 블록 생성 시간에 영향을 주게 되기 때문입니다.

# 2. 서비스체인

- 서비스 체인이란? 메인넷과 연결된 독립적으로 기동되는 블록체인입니다.
- 확장성/Private 상황을 고려하여 제공되는 서비스입니다.
- 주로 쓰이게 되는 경우는 다음과 같습니다.

> 주로 특별한 노드환경이 필요한 경우
 별도의 보안 수준을 맞춤형으로 설정해야 하는 경우(Private)
많은 처리량을 요구하나 메인넷 매번 메인넷에 배포하기에는 경제성이 낮은 경우


- 서비스 체인은 대략 아래의 이미지와 같은 형태를 나타냅니다.

![](https://cdn.steemitimages.com/DQmXPLVSpmx7U9rNfp1NjzadHsuUgJfXRRsTm2tmSvfK5ok/image.png)

- 서비스 체인은 메인체인과의 연결이 완전 자유롭게 할 수 있도록 되어 있지는 않습니다.
- 메인체인과는 제한된 트랜잭션만 사용될 수 있고, 클레이 전송도 제약조건이 추가 될 때에만 허용될 예정입니다.
- 서비스 체인은 예를 들자면, 실제 서비스 자체는 외부 서비스 이나, 클레이튼의 신뢰성을 이용하여, 중요한 부분만 클레이튼 블록체인을 이용하는 그런 경우에 클레이튼을 사용 할 수 있게 됩니다.

![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)


이론은 이번시간까지입니다. 다음 시간부터는 실제로 웹 IDE를 이용하여 실제로 클레이튼 테스트 넷에 스마트 컨트랙트를 등록하는 실습을 할 예정입니다. 클레이튼이나 개발을 잘 모르는 분들도 따라 할 수 있도록 구성해보도록 하겠습니다. 

### 여기까지 읽어 주셔서 대단히 감사합니다.

#### 지난 글
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 1편(클레이튼 특성, 합의)](/@happyberrysboy/klaytn-1)
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 2편(블럭생성 및 전파, 네트워크 구조)](/@happyberrysboy/klaytn-2)

![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)