---
title: '[kr-dev] 스팀커넥트 3 로그인 관련'
tags:
  - kr-dev
  - busy
  - jjm
  - mini
  - yesinfo
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)  안녕하세요! 해피베리보이입니다!!   오늘은 steemconnect 관련 개발글을 올려봅니다. ___  #### 1. ....."
date: 2019-03-31 17:38:42
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)

안녕하세요! 해피베리보이입니다!! 

오늘은 steemconnect 관련 개발글을 올려봅니다.
___

#### 1. Dependencies
library는 steemconnect 3.x로 해봅니다.(2.x 시절에 살짝 맛만 봐서 차이점은 아직..잘 모르겠습니당. 초기화 부분은 일단 다릅니다.)

##### dependencies 3.0.0-beta.1 
![image.png](https://ipfs.busy.org/ipfs/QmWezFNmRDBPeseB1svJsWfsQEeg71gXVdBbtqvQJy6sTN)

2.x 까지는 Initialize 을 이용하여 로그인을 하였지만, 3.x 부터는 new Client로 변경되었네요. 2.x는 deprecated 되었습니다.

![image.png](https://ipfs.busy.org/ipfs/QmSZp1W9AJvZJ4JGBn7c3RNN8RD3iUJumqAPqdGR4JptUD)


#### 2. 사용법

##### 2.x 샘플(오래간만에 @jungs 님 샘플입니다. 어디 계십니까 정스님!!! ㅠㅠ https://steemit.com/kr/@jungs/steemconnect-v2)
![image.png](https://ipfs.busy.org/ipfs/QmZzf7RpXisfAvszwRhZgQtYbdoEN3rYY6HnAWi4nMnYHT)

2.x 에서는 위와 같이 썼지만, 3.x 부터는 new Client로 Constructor을 이용하여 초기화 합니다.
##### 3.x 샘플(new Client)

![image.png](https://ipfs.busy.org/ipfs/QmYYwKqtEtrpj1T5rn7P47PGZvPHbNWsH2MVvUnb533jrZ)

##### config.json
![image.png](https://ipfs.busy.org/ipfs/Qmeu8VqnZhuqSMH2epcTCT7GYErXqvWbXdYVux5B1X95Du)


초기화 옵션에 저는 위 3가지만 필요했었지만, 실제로는 아래와 같이 총 5개가 있습니다.

![image.png](https://ipfs.busy.org/ipfs/QmNPCGXpRkECzLEkTd2enSTLJcSgGmNupsWPY3yfV1M4w6)

- apiURL : app으로 api를 호출 할 수 있도록 하는 것 같긴 한데, 아직 사용해보진 않아서 정확한 기능을 아직은 잘 모르겠습니다. 나중에 좀 더 공부해서 알게되면 알려드리겠습니다.
- app : SteemConnect에 등록된 app 명을 입력합니다. (https://app.steemconnect.com/apps 여기에 본인이 등록 했다면 해당 app명을 입력하시면 됩니다.)
- callbackURL : Steemconnect 인증 완료 후 callback URL을 입력합니다. 이 URL은 https://app.steemconnect.com/apps 에 등록된 URL만 callback 됩니다. 그렇지 않으면 oops 에러가 납니다.
- accessToken : accessToken 이미 있는 경우 인증 요청을 할 때 사용합니다.
- scope : steemconnect로 어떠한 권한을 부여할지 설정합니다.

#### 3. SteemConnect  이용 로그인 완료 자동로그인 처리

최근까지 좀 핫 했던 게임 drugwars.io 방법을 따라 했습니다. 
- SteemConnect 인증 완료 후 받게되는 accesstoken을 브라우져의 localstorage에 값을 저장
- 다음번에 로그인 시에 localstorage 에서 accesstoken 값을 얻음
- 이 accesstoken 값으로 로그인이 되면, 바로 로그인처리
- 값이 없거나 인증기한이 지나 인증이 되지 않으면 다시 SteemConnect로 로그인 처리

아이들이 옆에서 괴롭혀서 제대로 정리가 좀 안된 것 같네요 ㅠㅠ
혹시나 궁금하신 사항 있으시면 댓글 주십시오!!!

남은 주말 잘 보내셔요~~ ^^