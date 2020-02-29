---
title: '[Klaytn 5편] 클레이튼에 대해서 알아보자-실습편2(스마트 컨트랙트 작성 기본 with IDE)'
tags:
  - palnet
  - sct
  - steemleo
  - jjm
  - zzan
  - kr-dev
  - klaytn
  - liv
  - whan
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmPZqjSM966mqpB3eaKrHvXWRYu9MJKgtHWJo1zkXFAaXz/image.png)  안녕하세요, 햅뽀이입니다.  오늘은 어제 말씀드렸던대로 IDE(개발 툴)을 이용하여 실제로 클레이튼 스마트 컨트랙트를 작성하는 것에 대해서 포스팅을 합니다. 개발 내용은 얼마전에 먹튀로 유명했던 매직다이스의 룰....."
date: 2019-07-11 02:08:27
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmPZqjSM966mqpB3eaKrHvXWRYu9MJKgtHWJo1zkXFAaXz/image.png)

안녕하세요, 햅뽀이입니다.

오늘은 어제 말씀드렸던대로 IDE(개발 툴)을 이용하여 실제로 클레이튼 스마트 컨트랙트를 작성하는 것에 대해서 포스팅을 합니다.
개발 내용은 얼마전에 먹튀로 유명했던 매직다이스의 룰을 이용하여, 특정 숫자와 up/down을 선택하여 맞으면 클레이를 전송하는 기능을 만들어 보도록 하겠습니다.

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

## 1. 필요한 기능 정의(함수 정의)
- 제가 개발하려고 하는 것에는 아래와 같이 3개의 기능이 필요합니다.
- 스마트컨트랙트로 클레이를 송금하는 기능
- 스마트컨트랙트로 잔액을 불러 오는 기능
- 스마트컨트랙트로에서 사용자 계정으로 클레이를 보내는 기능

## 2. IDE로 접속
- https://ide.klaytn.com/ 사이트에 들어가보면 바로 개발을 할 수 있는 환경이 갖추어져 있습니다.(화면에 보이는 코드 내용은 아래 캡쳐화면가 다를 수 있으나 첨부터 다 다시 코딩을 할 예정이기 때문에 상관 없습니다.!)

![](https://cdn.steemitimages.com/DQmT39upvfHCRcG1SXiaXrmbGhsf9yXKB3eEQP7wzhRHJGb/image.png)

<br> 
## 3. Code
- 저희는 새로운 기능을 만들 것이기 때문에, 최초 상단의 ```pragma solidity >=0.4.24 <=0.5.6;``` 을 남겨두고 아래쪽은 모두 삭제를 합니다.(날짜에 따라 버전은 달라질 수 있습니다.)
- address 는 주소를 입력 할 수 있는 변수입니다.
- constructor 명령어는 생성자 역할을 합니다. 최초 1회만 불러 오기 때문에, 컨트랙트를 생성한 사람의 주소를 owner로 입력합니다.
- msg.sender 는 컨트랙트를 호출하는 계정을 불러오도록 되어 있습니다. 
- 일반 기본 컨트랙트 구조와 배포테스트를 위해 소스는 여기까지만 작성을 해봅니다.


```
pragma solidity >=0.4.24 <=0.5.6;

contract UpDownGame｛
    address public owner;
    
    constructor() public ｛
        // msg.sender은 컨트랙트를 호출하는 사람
        owner = msg.sender;
    ｝
｝
```

![](https://cdn.steemitimages.com/DQmYVkQCbzV7Z31gf7Ka2farcJVjzeg3MSxbZ5QDfaVy7Pi/image.png)
<br> 

## 4. 컴파일(Compile)
- 작성한 코드를 컴퓨터 언어로 변경시켜 주는 작업입니다.
- 우측에서 Solidity  버전을 선택한 후 (자동 컴파일을 원할 경우 Auto Compile 체크) Start to Compile를 클릭합니다.
- Solidity 버전은, 저희는 아주 간단한 기능만 사용 할 예정이므로 어느 버전을 사용해도 문제가 없을 겁니다.
![](https://cdn.steemitimages.com/DQmdfmBqNCid9Zc2adySxY6SPgWqK2XmUCpZRsGRa4RSyne/image.png)
<br> 

- 정상적으로 컴파일이 되면 아래그림처럼 UpDownGame이 생성됩니다.
![](https://cdn.steemitimages.com/DQmaESrtsazMsyBQ38w6buN557ifCQGG7eDe5uAVg6WP5k5/image.png)
<br> 

## 5. 배포(deploy)
- 우측의 Run 탭으로 이동합니다.
- Enviroment는 현재 클레이튼의 네트워크 종류를 말합니다. 현재 Mainnet은 존재하지 않고, 테스트 넷인 바오밥을 선택하시면 됩니다.

![](https://cdn.steemitimages.com/DQmNxczM8zxygWcxZ2BeBGySd7uCKZFhA6XV9tuN5NN8svh/image.png)
<br>

- Account에는 지난 시간에 만들었던 계정을 등록하시면 됩니다.
- 지난 시간에 만든 Private Key나 Ketstore를 이용하여 등록 할 수 있습니다.
![](https://cdn.steemitimages.com/DQmSHKe3SNCyyYKvaew1q2aqUbXtZfYmaRfbUgbTMbWMcKr/image.png)
<br>

- 그리고 아래 쪽에 Deploy를 클릭하시면 블록체인에 배포가 완료 됩니다. 
![](https://cdn.steemitimages.com/DQmcgLfD7uuM3PvGRCwggEb6qFgJ6hD1whV4aAaYS3P3DPw/image.png)
<br>

- 정상적으로 배포가 되면 아래쪽에 이렇게 표시가 됩니다. 
- 이렇게 저희는 블록체인위에 스마트 컨트랙트를 만들어서 배포를 완료하였습니다.!!!!!!(물론 아직 기능은 하나도 없습니다.)
- 추가 로직에 대해서는 다음편에 계속 진행하도록 하겠습니다.

![](https://cdn.steemitimages.com/DQmdmH16QuTZqHZPmBRGDUipBzPXD5gEKou1d94xsHFTKRf/image.png)






![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)

- 음.. 그런데... 개발을 모르는 분들도 따라 할 수 있게 해보려고 하였으나, 결국 Solidity 문법에서 설명이 불가능한 상황이 되어 버렸습니다. 생성자라던지, 함수라던지, 등등 말이지요. 하지만 앞으로는 어떤 코드들이 컨트랙트에 들어가 있는지, 왜 컨트랙트에다가 이러한 기능들을 입력해야 하는지 등에 대한 이해를 최대한 해드리는 방향으로 진행하도록 하겠습니다.



## 여기까지 읽어 주셔서 대단히 감사합니다.

#### 지난 글
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 1편(클레이튼 특성, 합의)](/@happyberrysboy/klaytn-1)
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 2편(블럭생성 및 전파, 네트워크 구조)](/@happyberrysboy/klaytn-2)
[[3편][Klaytn, 클레이튼] 클레이튼에 대해서 알아보자(코어셀, 서비스체인)](/@happyberrysboy/3-klaytn)
[[Klaytn 4편] 클레이튼에 대해서 알아보자-실습편1(계정,지갑생성)](/@happyberrysboy/klaytn-4-1)


![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)