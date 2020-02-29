---
title: '[2019. 9. 24] 스코판 사이트 수정 내역'
tags:
  - sct
  - sct-kr
  - sct-notice
  - zzan
  - liv
  - jjm
  - union
  - palnet
  - sct-dev
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/0x0/https:/\" />\r\n/cdn.steemitimages.com/DQmeVyCnkva2SjkjT5mk9XPo2BJzbK7szFE1pDqqAHrSBsC/WHALE_TITLE_COLORED_LOW.jpg)  안녕하세요, 햅뽀이입니다.  태풍이 지나가고 며칠 비가 내리더니 이제 완연한 가을이 온것 같습니다. 저녁에는 꽤나 쌀쌀하네요. 일교차도 크니 몸건강 잘 챙겨야 할 시기인 것 같습....."
date: 2019-09-24 23:56:12
---

![](https://steemitimages.com/0x0/https://cdn.steemitimages.com/DQmeVyCnkva2SjkjT5mk9XPo2BJzbK7szFE1pDqqAHrSBsC/WHALE_TITLE_COLORED_LOW.jpg)

안녕하세요, 햅뽀이입니다.

태풍이 지나가고 며칠 비가 내리더니 이제 완연한 가을이 온것 같습니다. 저녁에는 꽤나 쌀쌀하네요. 일교차도 크니 몸건강 잘 챙겨야 할 시기인 것 같습니다.

스코판 사이트에 간단한 수정내역들이 있었습니다. 소소하지만 끊임 없이 변화하고 있다는 것을 알아주셨으면 감사하겠습니다.

내역은 아래와 같습니다. 

![](https://steemitimages.com/640x0/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/819aaa9f-8c96-4afe-8307-323a32bc74ae/hr-sergio-ruiz.png)![](https://steemitimages.com/640x0/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/819aaa9f-8c96-4afe-8307-323a32bc74ae/hr-sergio-ruiz.png)

### 1. 뒤로가기시 사이트 먹통 에러 수정
- 오픈채팅방에 들어온 요청사항이었습니다.
- 사이트를 이리저리 다니다보면, 가끔 뒤로가기가 안먹혀 계속 새로고침을 해야 하는 경우가 생긴다고 했습니다.
- 이러한 현상을 일으키는 경우는 다양한 것으로 파악되지만, 일단 가장 문제가 되는 부분은 해결한 것 같습니다.
- 추가로 발생하시는 분은 제보해주시면 감사감사하겠습니다.


### 2. 따봉시 메세지 추가
- 따봉에 아이콘 모양까지 변경하였지만, 혹시나 하는 마음에 메세지까지 추가 하였습니다.
![](https://cdn.steemitimages.com/DQmd8KbXoUcJkqpLohfWWtU5t3417TM2jNiVrnBWMLsXiy3/image.png)
- 따봉처리시에 자동으로 댓글이 남겨지는 부분이 있는데, 따봉이 처리되는 동안, 메뉴얼로(그냥 유저가 댓글달기 눌러서 댓글을 다는 경우) 작성하는 경우, 자동으로 달리는 댓글과 충돌(3초 이내 2개의 댓글 작성)하여 둘 중에 하나만 작성되는 경우가 발생하였습니다.
- 그렇기 때문에 **따봉 완료처리** 메세지가 나타난 이후에 댓글을 작성해주실 것을 부탁드립니다
![](https://cdn.steemitimages.com/DQmSqwZPMPyd5DAH6CjXXCpwqqUVWUz8FRvt2Viv9m2x9WZ/image.png)

### 3. 한글화 추가 진행
- 사이트 몇몇 군데에서 한글화가 부족한 부분이 발견되어 추가로 수정하였습니다.
- 대부분 기존 스티미언들은 익숙한 용어이지만 뉴비분들이 알기 힘들 수도 있을 것 같아 작업을 완료 하였습니다.
![](https://cdn.steemitimages.com/DQmfGGcn4aARp5wHBG2atLeuAxFfQApkhYeciUQeZZuuhHR/image.png)
![](https://cdn.steemitimages.com/DQmT1PynY7dKC3Y7FQhhs8DaCXVLeFWDnFnHbJhoyNB6CKA/image.png)
![](https://cdn.steemitimages.com/DQmPGBW1GiXaPiPfssoYJEmiRNgpHg94JdRV583ffxo2FRG/image.png)
- **추가로 변경해줬으면 하는 부분이 있는 경우 알려주시면 감사하겠습니다.**


### 4. 댓글창 사이즈 업
- 댓글달기 눌렀을 때 뜨는 댓글창 크기가 작아서 기본 사이즈를 조금 키웠습니다.
- 댓글 창이 작아서 댓글을 적게 쓰는 것 같아서 한번 키워 보았습니다.(?)
##### 기존
![](https://cdn.steemitimages.com/DQmTR27uDDX6joXKyjhVfP4W4rNkTTuUB9QJ3YdGsBDkZnS/image.png)
##### 현재(가로 사이즈는 위와 동일합니다.)
![](https://cdn.steemitimages.com/DQmY4nA5VfmFUsKicECwnS9fVHCZxGZcEuHqLFwntfSrEmW/image.png)


![](https://steemitimages.com/640x0/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/819aaa9f-8c96-4afe-8307-323a32bc74ae/hr-sergio-ruiz.png)![](https://steemitimages.com/640x0/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/819aaa9f-8c96-4afe-8307-323a32bc74ae/hr-sergio-ruiz.png)


이상입니다. 추가로 필요한 기능이나 버그가 발견되면 제보해 주시면 감사하겠습니다!!
##### 오늘도 평안한밤 되시기를 바랍니다.