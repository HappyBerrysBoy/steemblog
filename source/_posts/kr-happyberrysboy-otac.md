---
title: '@otac님 단타를 위한 업비트 화면 위치 설정 스크립트'
tags:
  - kr
  - kr-dev
  - otac
  - busy
  - coinkorea
author: happyberrysboy
categories: dev
excerpt: "<img src=\"[image.png\" />\r\n안녕하세요, **힘없는** 해피베리보이입니다.  최근에 몇몇 분들은 아시겠지만 @otac 님이 단기간에 엄청난 수익을 얻었다는 글들 보신분들이 있으시지요. 무려... 100만원도 안되는 돈으로 한달만에 20억이 넘는 금액을... @otac님은 혼자 터득한 단타거래방법을 공개했지요. ([100만원으로 1억만들기 프로젝트](/@otac/100-1-1-10)) ....."
date: 2018-05-08 18:46:30
---

안녕하세요, **힘없는** 해피베리보이입니다.

최근에 몇몇 분들은 아시겠지만 @otac 님이 단기간에 엄청난 수익을 얻었다는 글들 보신분들이 있으시지요. 무려... 100만원도 안되는 돈으로 한달만에 20억이 넘는 금액을...
@otac님은 혼자 터득한 단타거래방법을 공개했지요.
([100만원으로 1억만들기 프로젝트](/@otac/100-1-1-10))

저도 한번 부자가 되고 싶어 도전해보려고 했는데..

오탁님은 **업비트**를 사용했는데 업비트에서 제공하는 UI가 오탁님의 단타매매에 완전 최적화 되어있지는 않아, 제 생각에 좀더 도움 될만한 화면으로 변경하는 스크립트를 만들어 봤습니다.

##### 원래 업비트 화면입니다.
![image.png](https://gateway.ipfs.io/ipfs/QmU8UtCjvCcCkQywiZsQwVsHmFJn8NAi83gEvGBcD4NUn2)
- 한눈에 보이지 않는 호가창(스크롤을 해야 위아래 호가들이 다 보임)
- 체결창은 더 아래에 있어 눈에 더 띄지 않고 거래량이 Height가 짧아 많은 경우 금새 창에서 사라지는 단점.
- 매수/매도는 호가주문에서 바로 하는경우가 더 편하므로 매수/매도 창은 아래로 내림.

___

#### 실행 스크립트
```
// 매수/매도 화면을 아래로 내림
$('.mainB .ty01 .halfB .rightB').wrap('<article></article>'); 
// 체결창을 호가창 옆으로 옮기기 위한 디자인 작업
$('.mainB .ty01 .tabB').wrap('<div class="rightB"></div>');
// 체결창을 호가창 오른쪽으로 옮기는 명령어
$('.mainB .ty01 .rightB:eq(3)').insertAfter('.mainB .ty01 .halfB .leftB');
// 체결창 백그라운드를 흰색으로
$('.mainB .ty01 .halfB .rightB:eq(1)').css('background-color','#fff');
// 호가창 사이즈를 한눈에 볼 수 있도록 사이즈 수정
$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB').css('height', '900px');
$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB div').css('height', '900px');
// 체결창 사이즈를 호가창과 동일하게 사이즈 수정
$('.askpriceB .scrollB').css('height', '900px');
$('.askpriceB .scrollB div:eq(0)').css('height', '900px');
// 체결창에 칼럼들 사이즈 조절
$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB .ty01 td').css('width', '25％');
```


#### 아래에는 스크립트에 익숙하지 않은 분들을 위한 사용방법이고요.. 익숙한 분들은 위 스크립트를 사용하시면 됩니다.(한번에 최종 화면으로 가시려면 위 스크립트를 그대로 console에 복사+붙여넣기 하시면 됩니다.)
___

#### 크롬브라우져 기준입니다.(Internet Explorer의 경우 11도 깔려있지 않아 테스트해보진 않았지만, 11이상에서는 될것으로 생각됩니다.)

## ++먼저 최종 적용된 화면은 아래와 같습니다.(결과부터 보여드려요~)++
##### 한화면에 모든 호가가 표시되도록 하였고, 체결현황 화면을 그 옆으로 옮겼습니다.
![image.png](https://gateway.ipfs.io/ipfs/QmST6E68BLin62iKrvemkGdjWZjZefBnbh6Gba7odGrLe6)

___

# 친절한 사용법!!
![image.png](https://gateway.ipfs.io/ipfs/QmPPAzRxXKBXmYFcB8RpUYnZJ3LndA3uiJwD3khcaQibth)

## 1. 업비트에 거래화면으로 들어갑니다. 그리고 **호가주문** 탭을 선택합니다.
![image.png](https://gateway.ipfs.io/ipfs/Qmdb9QBQNVNRp8ZHDkfD9Am3nurbwT8owv75cSUjPgKPzy)

## 2. **F12** 키를 눌러서 개발자 모드로 들어갑니다.(개발자 모드는 아래화면처럼 되어있습니다. 새창으로 뜨는 경우도 있고, 아래쪽에 뜨는 경우도 있으니 놀라지 마세요~~ 후훗!!)
![image.png](https://gateway.ipfs.io/ipfs/QmR9WHtEARYcQMJWXR46HKyS1jyJJcp5tyBSvSg5qfYJKG)

## 3. Console 탭으로 들어갑니다. 
![image.png](https://gateway.ipfs.io/ipfs/QmNzS4YFE5BPEPHcV8tBoa23cyqReowDvv5TYeGXPWd2he)

## 4. 가장 아래쪽에 명령어를 입력할 수 있는 곳이 있습니다. 그곳에 저 위에 있는 스크립트를 복사+붙여넣기를 하고 엔터키를 눌러 실행 시키면 적용됩니다.
![image.png](https://gateway.ipfs.io/ipfs/QmcUdeE1Btrijk4AjSLPWJTfCmsbsAW4MvLJiY2B5fXNE7)

## 5. 다시 F12 키를 눌러서 개발자모드 화면을 닫습니다..!! 또는 오른쪽 위의 X 를 클릭하여 개발자 창을 종료합니다.
![image.png](https://gateway.ipfs.io/ipfs/QmUMnA2a6sfdPKdEzmvz4r1BQA8usCxFmJipU7Kua4S1vk)

## 6. 눈이 빠지도록 째려보고 노려보고, 머리가 뽀개지도록 계산하고 외워서, 이익을 극대화 합니다..!!
![image.png](https://gateway.ipfs.io/ipfs/QmT5bSnpxEBf2q9SzvmZKuMVett3JU2NTBEgKXV7ckBAoQ)

___
하지만 저에겐 아직은 맞는 매매방법은 아닌것 같아요....
좀더 시간적으로 여유 있고 하신 분들은... 도전을 해보셔도 좋을 듯 싶습니다..!!

혹시나 본인의 모니터는 30인치라서 체결창을 더 늘리고 싶거나 하면, 스크립트에 있는 900px 대신 좀더 큰 수치를 입력하셔도 됩니다.
하나씩 스크립트를 순서대로 실행해보면서 조금씩 변형해서 사용해도 되니.. 한번 참고해보실분들은 참고해보시길 바래요..!!!

### 모두가 부자가 되는 그날까지... 화이팅입니다..!!
### 추가로 필요한 배치 같은게 있으면 댓글 주세요.. 어렵지 않으면 해드릴게요..
### 중간에 체결 누적량 계산도 해보려 했는데 일단 오늘은 여기까지...
###### 아직 후유증은.. 진행중입니다.. 극복 노력중..  ㅠㅠ