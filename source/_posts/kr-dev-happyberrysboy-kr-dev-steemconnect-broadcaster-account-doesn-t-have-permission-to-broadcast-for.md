---
title: >-
  [kr-dev, steemconnect] broadcaster account doesn't have permission to
  broadcast for 에러 관련
tags:
  - kr-dev
  - jjm
  - mini
  - busy
  - yesinfo
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/ipfs.busy.org/ipfs/Qman2EX2PHQ4YpS5QRttNh6yBApcQQVc3YD2iheeThsdS8)  안녕하세요, 해피베리보이입니다.  오늘은 어제 개발할 때 저를 힘들게 만들었던 오류!!를 가지고 포스팅을 드리려합니다.  ___  어제 steemconnect를 이용하여 \"broadcast\" 명령어로 custom_json 값을 날리려고....."
date: 2019-04-25 11:16:48
---

![](https://steemitimages.com/640x0/https://ipfs.busy.org/ipfs/Qman2EX2PHQ4YpS5QRttNh6yBApcQQVc3YD2iheeThsdS8)

안녕하세요, 해피베리보이입니다.

오늘은 어제 개발할 때 저를 힘들게 만들었던 오류!!를 가지고 포스팅을 드리려합니다.

___

어제 steemconnect를 이용하여 "broadcast" 명령어로 custom_json 값을 날리려고 하는데 자꾸 저 제목 에러가 뜨는겁니다.

```
broadcaster account doesn't have permission to broadcast for @appname
```

영어가 짧은 저는.. 음.. 브로드캐스터 하는 계정이 권한이 없다라... 앱이 권한이 없나... steemconnect로 로그인 한 그 계정에 권한이 없나... 한참 헷갈려 했네요..

그런데 원래 앱에는 그런 권한 관련해서 설정하는 곳이 없기 때문에, 로그인 한 계정 탓이라고 생각하고 끊임없이 소스를 바꾸고 또 바꾸고 또 바꾸고... 몇시간을 허비 했더랬죠..

구글에 저 에러로 검색을해도 마땅한 글도 하나도 안나왔었고 말이죠..
steemconnect 오픈소스를 다운 받아도 보고 이런 저런 것들을 다 해보다가.. 
@fabien의 글을 찾게 되었죠..!! 스팀커넥트 개발자!!

https://steemit.com/steemconnect/@fabien/major-incoming-changes-on-steemconnect

이글입니다. 제목은 "Major incoming changes on SteemConnect" 이고요.

조금 읽어보니...


>"In the process of making SteemConnect more decentralized we’ve decided to give you ownership of this account."

스팀커넥트를 더 탈중앙화 하기 위해 앱 권한을 계정에게 넘겨준다.

>"By default the app account will delegate posting authority to the account @steemconnect."

앱계정은 @steemconnect 계정에게 posting 권한을 위임해야한다.

라고 되어 있더군요..

그래서 그제서야 [discord 개발자 방](https://discord.gg/NCZMVev)을 찾아가서.. 동일 건에 대한 오류메세지를 검색해보니 앱 계정에서 스팀커넥트로 권한을 줘야 한다는 글을 찾게 되었네요..!!! ㅠㅠ

![image.png](https://ipfs.busy.org/ipfs/QmRgZnSgZgg2K7Z1F7hvWRjXWnDA4rLAqaHZmU2ZnVib6o)

![image.png](https://ipfs.busy.org/ipfs/QmNyGzShBDRFin7eKJTaHLzTvUrTUpTiftvYiT25n7UWSS)

그랬습니다...
http://steemconnect.com/authorize/@steemconnect
이 링크를 클릭하고 앱을 관리하는 계정으로 posting 권한을 넘겨주니까 해결 되었습니다.

 텔레그램 한국인 개발자방에 문의 했어도 바로 아시는 분들이 많으셨을 것 같았는데, 시간이 새벽 2시가 넘은 상태로 묻기가 좀 그랬었네요.

혹시나 다른 개발자 분들이 이 에러를 맞이 하게 되었을 때, 구글검색에서 이 글이 찾아져서 바로 해결되길 바라는 마음으로 올려봅니다..

# 요약
- steemconnect로 broadcast 명령어를 사용 할 때!
- broadcaster account doesn't have permission to broadcast for 에러가 뜨면!
- http://steemconnect.com/authorize/@steemconnect 링크를 눌러서 posting 권한을 위임해줘라!!

끝!! 이상입니다.
오늘도 즐거운 코딩 하세요~~ ㅋ