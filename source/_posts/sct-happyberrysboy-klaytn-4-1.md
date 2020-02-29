---
title: '[Klaytn 4편] 클레이튼에 대해서 알아보자-실습편1(계정,지갑생성)'
tags:
  - sct
  - jjm
  - zzan
  - kr-dev
  - klaytn
  - liv
  - steemleo
  - palnet
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://cdn.steemitimages.com/DQmPZqjSM966mqpB3eaKrHvXWRYu9MJKgtHWJo1zkXFAaXz/image.png\" />\r\n  안녕하세요, 햅뽀이입니다.   오늘은 클레이튼에 대한 정보 네번째 시간입니다. 오늘은 실제로 BApp을 만들기 위해  필요한 준비로 테스트넷(baobab testnet)에서 지갑만들기를 진행해볼 예정입니다.  ** BApp 이란? 블록체인에서 나온 대부분의 Application들은 Dapp(Decentralized Application)이라고 많이 불려....."
date: 2019-07-10 02:03:21
---

![](https://cdn.steemitimages.com/DQmPZqjSM966mqpB3eaKrHvXWRYu9MJKgtHWJo1zkXFAaXz/image.png)

안녕하세요, 햅뽀이입니다. 

오늘은 클레이튼에 대한 정보 네번째 시간입니다.
오늘은 실제로 BApp을 만들기 위해  필요한 준비로 테스트넷(baobab testnet)에서 지갑만들기를 진행해볼 예정입니다.

** BApp 이란? 블록체인에서 나온 대부분의 Application들은 Dapp(Decentralized Application)이라고 많이 불려져 왔으나  클레이튼에서는 BApp(Blockchain Application)이라고 호칭하고 있습니다.


![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

## 1. 클레이튼 블록체인 관련 추가 정보
- 클레이튼은 이더리움의 비잔티움 버전의 Fork 버전입니다.
- 이더리움의 web3.js와 유사한 caver.js를 사용하고 있습니다.
- 스마트컨트랙트 작성에 이더리움에서 사용하는 언어 Solidity를 이용합니다.(Solidity는 Javascript와 유사한 문법을 가지고 있습니다.)
- 트러플 프레임워크 란것을 사용하고 있습니다.
- 클레이튼 사이트에서는 개발툴([IDE](https://ide.klaytn.com/)), 지갑([Wallet](https://baobab.wallet.klaytn.com/)), 블록정보([Scope](https://scope.klaytn.com/))를 제공하고 있습니다.



## 2. 클레이튼 계정/지갑 생성
- https://baobab.wallet.klaytn.com/ 사이트로 접속합니다.!!
![](https://cdn.steemitimages.com/DQmVwrs2p8LinjGMADBn5SEH4KHoeniKsWcAA5BfgSJpurL/image.png)
<br>

- Create Account를 클릭하면 아래와 같은 화면이 나옵니다.
- Keystore File을 위한 패스워드를 입력합니다. 패스워드는 아래조건에 따라 강력하게 설정하셔야합니다.
- 여기서 잠깐!! keystore란? 지갑을 사용하기 위한 Private Key를 비밀번호로 암호화한 텍스트/파일입니다. 간단히 말하자면 지갑을 사용하는데 Private Key(PK)가 필요한 것은 아실겁니다. 하지만, 이 PK를 바로 노출 하는 것은 위험 하기 때문에, PK + 입력한비밀번호를 합쳐서 암호화 한 파일을 말합니다. 추후에 지갑을 Import 할때에는 Keystore 값을 입력하고, 비밀번호까지 입력해야합니다.
![](https://cdn.steemitimages.com/DQmcncY8UTQcQxScJ4u6yBfAD9DHeteLCmAYrF2WynBEZRh/image.png)
<br>

![](https://cdn.steemitimages.com/DQmeQr63bDxE1uHy4B41SBXQzYm79AmQ4xrubm5WVXXFAf9/image.png)
<br>

- Keystore 파일을 저장하는 단계입니다. Keystore 파일을 잘 보관해야 함은 두말할 나위 없습니다. 일단 지금은 테스트 단계이니 큰 부담은 안가지셔도 됩니다.
![](https://cdn.steemitimages.com/DQmSnpmb3JDCT1yGF3zQozEf7HT2SYGGCbj5fjbkPq7Wxxf/image.png)
<br>

- Keystore까지 저장하면 완료되었습니다. 나타나는 **Private Key와 Klaytn Wallet Key를 잘 저장해 놓으셔야합니다**.!!
- 저장을 완료 하였으면 아래쪽에 View Account Info를 클릭합니다.
![](https://cdn.steemitimages.com/DQmeXhYh91ZuL7nV9BDKzFcuZ3qK9y5mmWXceYJ2sUhzJqD/image.png)
<br>

## 3. 지갑에 접근 및 지갑 탐색

- 로그인 화면이 나타납니다. 로그인은 두가지 옵션으로 가능합니다.
- Sign-in Using Private Key : 계정생성 Step 3단계에서 보여주었던 Private Key를 바로 입력해서 로그인을 합니다.
- Sign-in Using Keystore File : Keystore 파일을 불러오고 추가로 비밀번호를 이용하여 로그인 합니다. Private Key를 분실 한 경우 Keystore + 비밀번호로 로그인이 가능한거지요..!! 
![](https://cdn.steemitimages.com/DQmWcH6u5NUs71vHKwG1GTooYJB3qdNsfsUKpe5zur5Wpv9/image.png)
<br>

- 로그인을 완료 하면 아래와 같은 화면이 나타납니다. 지갑주소(0x740a8d3c86c00c519f14d410628aa0af5c357255), Keys, Transaction List, Balance, Send Token 등을 확인 할 수 있습니다.
![](https://cdn.steemitimages.com/DQmZfZMJxZdJoucMo9xeGqSGMkWJusEy2cAXWEqcXmdAVsq/image.png)
<br>

- 좌측의 KLAY Faucet를 클릭하면 테스트 서버에서 테스트용으로 사용할 Klay 토큰을 받아 볼 수 있습니다. 
- Run Faucet를 클릭하면 5개의 테스트용 Klay를 받을 수 있습니다. 그리고 한번 받으면 24시간 후에 다시 받으실 수 있습니다.
![](https://cdn.steemitimages.com/DQmNvaEkV3TBbmJyyhyDKpK8bXh87H1Ba8UGNtNuooZAnrU/image.png)
<br>

## 4. Klay & Token 전송 테스트 

- Send KLAY & Token 을 이용하여 토큰 전송을 테스트 해보도록 하겠습니다.
- 좌측에서 KLAY or Token(지금은 없지만)을 선택합니다.
- 우측의 To Address에 주소를 입력합니다.(저는 이전에 만들어 놓은 계정이 있어서 그리로 보내보았습니다.)
- 전송에 사용되는 Transaction Fee가 존재합니다. 0.000625 KLAY가 전송에 사용되는 고정 수치 입니다. 이 값은 아래의 Gas Price * Gas Limit로 결정되어 집니다.
- Gas Price : 트랜잭션 처리를 위해 드는 비용은 항상 25Ston입니다.(Ston?? 단위?? 아래에서 다시 설명 드리겠습니다.)
- Gas Limit : 트랜잭션을 처리하면서 들어가는 가스의 최대 용량(?)을 말합니다. 트랜잭션을 처리하는데 무한 루프가 존재하여 모든 노드가 정지되지 않도록 하기 위해서, Gas Limit 만큼만 동작하고 그 이후에는 트랜잭션 처리를 하지 않게 됩니다.
![](https://cdn.steemitimages.com/DQmPfHkuJBZX3zXbAG2ogMFZPTuYth8a2JB7cchdy4HFMsP/image.png)
<br>

- 여기서 잠깐? 단위가 이상하지요? Ston만 존재하는 것이 아니라 클레이튼에서는 다양한 단위를 미리 정의 해놓았습니다.
- peb가 가장 작은 단위이고 TKLAY가 가장 큰 단위입니다. 일반적으로 알려져 있는 KLAY가 10의 18승 정도이고, Ston은 10의 9승으로 KLAY 보다는 "0"을 9개 뺀것만큼 적은 수치입니다.
![](https://cdn.steemitimages.com/DQmVXhYkMe9P4Gtgw5QTnLFPhtvhV95Dw5newQLP3tmgLzb/image.png)
<br>

- Send Transaction을 클릭하여 토큰을 전송합니다.
- 내용을 확인하고 Yes, I'm sure. 를 클릭하면 토큰전송이 완료됩니다.
![](https://cdn.steemitimages.com/DQmZbHMEjzoyxc54etJDPgJ6qe7KxG5hzcsPHRSkUGQ8wBX/image.png)
<br>

- 토큰 전송 완료 메세지가 나타나고, View Transaction Info를 클릭하여 실제 블럭 정보를 확인 할 수 있습니다.
![](https://cdn.steemitimages.com/DQmbWsYUu3QWdJCRo2Y4d3hjcqN9uacncY9dFmEhdeaCRPe/image.png)
<br>

- 1 KLAY가 To Address로 전송된 것을 확인 할 수 있습니다.
- 여기서 우측 중간에 보면 Gas Used가 있습니다. 그 아래에는 Gas Limit가 있고요. Gas Limit(25,000)까지 여유가 있는데 21,000까지만 쓰고 트랜잭션을 처리 했다는 말입니다.
- 그래서 실제로 사용되어진 수수료는 0.000525KLAY가 소모 된것을 확인 할 수 있습니다.
- 이는 이더리움에서도 마찬가지로 작동되는 부분입니다.
![](https://cdn.steemitimages.com/DQmYKY3R4tWDcPWUuGF38MWyCgAxjxc3hgibCpD4WhPctX1/image.png)
<br>

### 계정 생성은 여기까지해서 완료하겠습니다.

![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)

- 클레이튼을 사용해본 결과, 일단 이더리움보다 훨씬 편한 User Interface가 돋보입니다. 예전에 2017년에 이더리움 한번 써보려고 하면, 뭔가 많이 복잡 했었는데, 클레이튼은 알아서 잘 이끌어 주는 기분이 듭니다. UI가 깔끔하기도 하고 말이죠.
- 이렇게 점점 블록체인 기술은 우리 생활에 다가오고 있는 것 같습니다. 올해 클레이튼 메인넷 출시 이후 나올 Bapp들도 기대되고, 내년에는 아마 폭발적으로 BApp들이 출시되지 않을까 예상해봅니다.
- 현직 개발자로서.. 요즘처럼 개발자가 우대 받았던 적은 적어도 제가 일했던 10년간은 없었던 것같습니다. 부디 지금만큼 또는 그이상 공부하고 해서 제대로된 서비스를 한번 만들어 내어 보길..... 희망하고.. 노력해보겠습니다.

## 여기까지 읽어 주셔서 대단히 감사합니다.

#### 지난 글
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 1편(클레이튼 특성, 합의)](/@happyberrysboy/klaytn-1)
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 2편(블럭생성 및 전파, 네트워크 구조)](/@happyberrysboy/klaytn-2)
[[3편][Klaytn, 클레이튼] 클레이튼에 대해서 알아보자(코어셀, 서비스체인)](/@happyberrysboy/3-klaytn)


![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)