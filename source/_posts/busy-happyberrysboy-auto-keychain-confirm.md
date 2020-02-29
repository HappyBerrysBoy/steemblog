---
title: 크립토게임을 Auto로 돌려보자!! (keychain 자동 confirm 기능 포함)
tags:
  - busy
  - kr-dev
  - jjm
  - mini
  - yesinfo
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)  안녕하세요, 해피베리보이입니다.  음.. 열심히 다이스를 굴리고 있습니다. 블랙잭도요.. 절대 도박이 좋아서 하는게 아....."
date: 2019-04-11 13:37:57
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)

안녕하세요, 해피베리보이입니다.

음.. 열심히 다이스를 굴리고 있습니다. 블랙잭도요..
절대 도박이 좋아서 하는게 아니라, 투자라는거 잊지 말아주십시옹!! ^^;;

근데 이게 매번 keychain으로 눌러 주는게 보통일이 아니잖아요, 그래서 또 찾아보았지요. 자동으로 할 수 있는 방법을요.
근데 이게 소스를 수정해서 해야 하는 부분이므로, 정말 해보고 싶으신 분들은 해보시고, 위험하다 생각되시면 삼가주시기 바랍니다. 제가 책임 질 수 없는 상황이 안오길 바라 봅니다..!!

1단계인 keychain 자동화만 해도 각종 귀찮은 keyChain 수동 컨펌에 비해 많이 편합니다.  

___

일단 두단계로 나눠집니다.

#### 1. keychain 자동 confirm
1) keychain 프로그램 소스를 다운 받는다.
 - https://github.com/MattyIce/steem-keychain 이분이 steem keychain을 만든 분입니다..!! 믿을만한 분이쥬?
 - Clone or download를 클릭하고 Download ZIP을 눌러서 소스를 다운 받는다.(원래 keychain을 만든 분이기 때문에 이 소스는 믿을만한 소스라고 판단 가능합니다!!)
 ![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/nacGWI1I-image.png)
 - 메모장으로 steem-keychain-master\js\dialog.js 파일을 열어본다.
 - 290 라인에 아래 소스를 추가 하고 저장한다. 아래 그림 참조. (참고로 뒤에 있는 숫자 2000은 확인 창이 뜬 뒤에 2초만에 자동컨펌이 이루어 진다는 말인데, 더 천천히 컨펌을 하고 싶으면 변경하셔도 됩니다. 원하는 초 * 1000으로 하면 적용됩니다.) 정해진 2초 안에 Cancel을 하면 취소처리됩니다..!!
```
 setTimeout(function() ｛ $('#proceed').click() ｝, 2000); 
```
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/6Z2jXyRY-image.png)
 - 소스 변경후 파일을 저장하고 chrome을 열고, 확장 프로그램을 선택한다.(또는 그냥 주소창에 chrome://extensions/ 을 입력한다.)
 ![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/V5h6S6KD-image.png)

 - 우측 상단에 개발자 모드를 활성화 시킵니다.
 ![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/v33jxNqd-image.png)

- 기존에 keychain이 깔려 있으셨던 분들은 기존 keychain을 비활성화 시켜주셔야합니다.
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/S15NzsTf-image.png) 

-  상단에 "압축해제된 확장 프로그램을 로드합니다. 를 클릭하고, 아까 소스 수정한 폴더를 선택하시면, 아래에 확장 프로그램이 추가가 됩니다.
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/XEsOPy9K-image.png)
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/uzS7FkCR-image.png)

- 그러면 아래쪽에 방금 선택한 keychain이 추가가 됩니다. 그리고 활성화 시킵니다.(아마 기본이 활성화)(참고로 저는 Steem keychain "Test" 라고 뜨는데, 제가 임의로 제목만 바꿔서 그런겁니다. 별건 아닙니당.)
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/8VgOINGI-image.png)

### keychain 자동 컨펌은 여기까지  완성!!

___

#### 2. 다이스 Auto스크립트(https://kryptogamers.com/dice 여기에서만 사용되는겁니다. 다른 다이스 사이트는 안되요!!)
- 다이스 사이트로 갑니다.(https://kryptogamers.com/dice)
- 크롬에서 F12를 눌러 주면 개발자 모드가 활성화가 됩니다.
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/Dr7nM9PU-image.png)
- Console 탭으로 가서 아래 명령어를 입력하면 엔터를 치면 바로 자동으로 다이스가 실행됩니다.
```
setInterval(()=>｛document.querySelector('.btn-block').click()｝, 10*1000);
```
### 완료!!!!!

### 주의사항..!!  위의 스크립트를 여러번 실행하시면 중첩되서 여러번 실행이 됩니다. 한번만 실행 하셔야합니다.
### 한번 실행하고 10초 기다리면 자동실행되시는걸 보실 수 있습니다. 
### 중단하는 방법은 F5 Refresh!!
### keychain은 계속 자동 컨펌 상태이기 때문에 dice 사이트만 Refresh 해주시면 됩니다.

___

다이스는 스팀을 잃을 수 있는 위험한 것이니 너무 빠져드시지는 마시길 바랍니다..!!
다시한번 말씀드리지만.. 저는 그냥 투자로 하는겁니다!! 투자!!