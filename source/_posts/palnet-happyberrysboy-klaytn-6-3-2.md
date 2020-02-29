---
title: '[Klaytn 6편] 클레이튼에 대해서 알아보자-실습편3(스마트 컨트랙트 작성2)'
tags:
  - palnet
  - solidity
  - sct
  - kr
  - jjm
  - zzan
  - kr-dev
  - klaytn
  - liv
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmPZqjSM966mqpB3eaKrHvXWRYu9MJKgtHWJo1zkXFAaXz/image.png)  안녕하세요, 햅뽀이입니다.  오늘은 지난시간에 이어 스마트컨트랙트 실제 소스를 짜보도록 하겠습니다. 잘 이해가 안되시더라도, 대충 블록체인에 스마트컨트랙트가 이런식으로 작성이되고, 체인에서 돌면서 요청처리가 되....."
date: 2019-07-17 01:50:00
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmPZqjSM966mqpB3eaKrHvXWRYu9MJKgtHWJo1zkXFAaXz/image.png)

안녕하세요, 햅뽀이입니다.

오늘은 지난시간에 이어 스마트컨트랙트 실제 소스를 짜보도록 하겠습니다. 잘 이해가 안되시더라도, 대충 블록체인에 스마트컨트랙트가 이런식으로 작성이되고, 체인에서 돌면서 요청처리가 되는구나 하고 이해해주시면 감사하겠습니다. ^^;;

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

## 1. 필요한 기능 정의
- 제가 개발하려고 하는 것에는 아래와 같이 3개의 기능이 필요합니다.
- 계정의 잔액을 확인하는 기능
- 스마트컨트랙트로 클레이를 송금하는 기능
- 스마트컨트랙트로에서 사용자 계정으로 클레이를 보내는 기능

## 2. 계정의 잔액을 확인하는 기능

```
// 현재 계정의 잔액을 확인
// view는 읽기 전용 함수라는 명령어
// uint 를 반환
function getBalance() public view returns (uint)｛
    // address(this) 현재 조회한 계정
    // balance는 잔액
    return address(this).balance;
｝
```


## 3. 스마트컨트랙트로 클레이를 송금하는 기능
- 게임 참여를 위해서 스마트컨트랙트로 토큰을 송금하는 함수입니다.
```
// 참여자가 컨트랙트로 토큰을 송금하는 함수
// payble명령어는 송금하는 함수에는 필수적으로 쓰여야 함. 
function deposit() public payable｛
   // 유효성 검사(조건체크)로 조건이 맞지 않으면 함수가 실행되지 않음.
   require(msg.sender == owner);
｝
```

## 4. 스마트컨트랙트로에서 사용자 계정으로 클레이를 보내는 기능
- 스마트컨트랙트에서 보유하고 있던 클레이를 사용자가 게임에서이긴 경우 다시 반환됩니다.
```
// 컨트랙트에 존재하는 토큰을 사용자 계정으로 송금
// amount 전송할 클레이양
function transfer(uint amount) public returns (bool)｛
    // 유효성 검사(전송하려는 양이 현재 잔액보다 많진 않은가)
    require(getBalance() >= amount);
    // 토큰을 전송
    msg.sender.transfer(amount);
    return true;
｝
```

## 5. Compile/Deploy/Test
- 컨트랙트를 작성하면 IDE에서 바로 컴파일/배포는 물론 테스트까지 가능합니다.
- 지난 시간에 했었던 compile/deploy가 완료되면 deployed contracts에 컨트랙트가 표시됩니다.
- 화살표로 펼쳐보면 우리가 만들었던 컨트랙트 함수들이 모두 표시가 되고, 테스트도 가능합니다.

![](https://cdn.steemitimages.com/DQmQ65uZJ6e5AB6hjXFZaZTKZHs5UKGop1GQ1vCpkduD2bE/image.png)

- deposit 함수를 이용하여 전송한 로그입니다.
- peb(가장 낮은 화폐단위) 단위로 자동으로 변환 후 계산
![](https://cdn.steemitimages.com/DQmcm3aUTPw4zdEtDRtjuxZ7gUMqRJXxBM1ntH6GZqhrzQZ/image.png)



- 전체 소스
```
contract UpDownGame｛
    address public owner;
    
    constructor() public｛
        owner = msg.sender;
    ｝
    
    // 현재 계정의 잔액을 확인
    // view는 읽기 전용
    // uinit 를 반환
    function getBalance() public view returns (uint)｛
        // address(this) 현재 조회한 계정
        // balance는 잔액
        return address(this).balance;
    ｝
    
    // 토큰을 송금하는 함수
    // payble는 송금하는 함수에는 필수적으로 쓰여야 한다.
    function deposit() public payable ｛
        // validation 조건이 맞지 않으면 함수를 종료
        require(msg.sender == owner);
    ｝
    
    // amount 전송할 클레이양
    function transfer(uint amount) public returns (bool)｛
        require(getBalance() >= amount);
        msg.sender.transfer(amount);
        return true;
    ｝
｝


```


![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)

- 스마트컨트랙트로 만들어져야 할 부분은 의외로 위와같은 3개의 함수로 생각 보다 적습니다. 나머지는 게임을 구현하는 곳에서  게임의 승리여부를 판단하여, 조건에 맞는 스마트컨트랙트롤 호출하도록 되어 있는 것이지요.
그리고 스마트컨트랙트는 불필요한 소스를 최대한 배제하고, 필요한 소스만 입력하는 것이 수수료를 줄이는 지름길입니다. 참고하시기 바랍니다.



## 여기까지 읽어 주셔서 대단히 감사합니다.

#### 지난 글
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 1편(클레이튼 특성, 합의)](/@happyberrysboy/klaytn-1)
[[Klaytn, 클레이튼] 클레이튼에 대해서 알아보자 2편(블럭생성 및 전파, 네트워크 구조)](/@happyberrysboy/klaytn-2)
[[3편][Klaytn, 클레이튼] 클레이튼에 대해서 알아보자(코어셀, 서비스체인)](/@happyberrysboy/3-klaytn)
[[Klaytn 4편] 클레이튼에 대해서 알아보자-실습편1(계정,지갑생성)](/@happyberrysboy/klaytn-4-1)
[[Klaytn 5편] 클레이튼에 대해서 알아보자-실습편2(스마트 컨트랙트 작성1 )](/@happyberrysboy/klaytn-5-2-with-ide)


![](https://steemitimages.com/DQmRQeSKNvf5L6LcZHufnihnBJSL1CfZ3hEHDcJNuFRPZnu/％EA％B5％AC％EB％B6％84％EC％84％A0_％EA％BD％83.png)