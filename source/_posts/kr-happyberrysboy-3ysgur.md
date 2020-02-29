---
title: '[이지스팀잇]디자인 된 타이틀을 “즐겨찾기”에 추가해서 사용해보자..!!'
tags:
  - kr
  - kr-dev
  - easysteemit
  - busy
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemit.com/kr/@easysteemit/2\" />\r\n안녕하세요, 해피베리보이입니다.  며칠 전부터 쓰던 일기에 \"1, 2, 3..\" 숫자들을 약간 디자인된 걸로 작성을 했었더랬죠. 여기 [이지스팀잇 마크타운, 고오급 편집팁 (2) - 템플릿 대방출]( 에서 이쁜 부분을 발췌해서 사용을 했었어요.  그런데 종종 그걸 사용하려면 또 해당 글을 가서 해당 부분을 캡쳐해 와서 써야 하다보니 조금은 불편한 감이 있어....."
date: 2018-07-04 13:44:54
---

안녕하세요, 해피베리보이입니다.

며칠 전부터 쓰던 일기에 "1, 2, 3.." 숫자들을 약간 디자인된 걸로 작성을 했었더랬죠.
여기 [이지스팀잇 마크타운, 고오급 편집팁 (2) - 템플릿 대방출](https://steemit.com/kr/@easysteemit/2) 에서 이쁜 부분을 발췌해서 사용을 했었어요.

그런데 종종 그걸 사용하려면 또 해당 글을 가서 해당 부분을 캡쳐해 와서 써야 하다보니 조금은 불편한 감이 있어, 즐겨찾기에 추가하고 클릭해서 내용을 붙여 넣을 수 있도록 만들어 보았습니다용용~!!


<center><h3>적용방법</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.pngBEST</center><br>

예전에 @asbear 님이 쓰셨던 방법이 갑자기 떠올라서 적용해 봤습니다.
즐겨찾기에서 스크립트를 작동하게 할 수 있더라고요..
그래서 해봤습니다.

크롬기준입니다..!!

- 크롬 우측 상단에 **점세개 메뉴 - 북마크 - 북마크 관리자** 로 들어갑니다.
![image.png](https://gateway.ipfs.io/ipfs/QmWgT2eYbzanTzpsuugF25ukD9ox6VQHCnQ2kG7vKGN9By)
- 화면 바깥쪽 아무 맨땅에서 **마우스 우클릭 - 새 북마크 추가** 를 해줍니다.
![image.png](https://gateway.ipfs.io/ipfs/QmWgC5PcNT2uqwGh7TA6K2YrKpC5ciio2s8AzGRS57RYPw)
- 북마크 이름에는 본인이 원하시는 이름을 쓰시고 아래쪽 URL 에는 아래 스크립트를 입력합니다. 그리고 저장을 누릅니다.
- Steemit / Steemkr / Busy 사이트마다 스크립트가 조금씩 달라서 각자 본인이 사용하시는 사이트에 맞는 스크립트를 입력하시면 됩니다.

![image.png](https://ipfs.busy.org/ipfs/QmR7NH7La9YHwBmDKVvCWheGtYqYxvxQ6WFkxFP91CsTCE)


# Steemit 용 script
```
javascript:function a()｛let area=document.getElementsByClassName('smi-gif-picker-textarea')[0];area.blur(); area.value=area.value + '<center><h3>' + prompt() + '</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.pngBEST</center><br>';｝a();
```

# Steemkr 용 script
```
javascript:function a()｛let area=document.getElementsByName('body')[0];area.blur(); area.value=area.value + '<center><h3>' + prompt() + '</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.pngBEST</center><br>';｝a();
```

# Busy 용 script
```
javascript:function a()｛let area=document.getElementById('body');area.blur(); area.value=area.value + '<center><h3>' + prompt() + '</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.pngBEST</center><br>';｝a();
```

<br>
<br>
<center><h3>사용법</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.pngBEST</center><br>

제가 지금 busy를 이용하고 있으므로 busy에서 쓰는 법을 참고해서 보여드리겠습니다.

1.  글작성 화면으로 들어 갑니다.
![image.png](https://ipfs.busy.org/ipfs/QmdhNxhZidzPZ1GEHTR9cbRzKB3M9EBFcYd6tutNmndCYe)

2. 즐겨찾기에서 등록하신 메뉴를 클릭합니다.
![image.png](https://ipfs.busy.org/ipfs/QmVRijKYc7o4QfrgUoP12Y44Q2NkhCAbRMVjxXLz1F8vLM)

3. 입력 할 수 있는 창이 하나가 활성화 되고, 표시 할 **Title**을 입력하시고, 엔터!!를 하시면, 글작성 화면 제일 아래에 해당 부분이 추가되게 됩니다.
![image.png](https://ipfs.busy.org/ipfs/QmR4mLPLTmmB9Kjii2FTsCtQEFkYibBmn7K4Aarr4JDNEy)

<br>
요런식으로 스크립트가 입력됩니다.
![image.png](https://ipfs.busy.org/ipfs/Qmb81kXQHnTSwc8HeYXrkzmgZsguY5XjMzGEYcAAQwpAAk)
<br>
아래쪽에 미리보기를 보시면 요로코롬~ 잘 나타나는 걸 보실 수 있습니다..!!
![image.png](https://ipfs.busy.org/ipfs/QmYXR4eNXHWZbrMws9Zn7g1BWyaEBV2tfRgJhXEKub7fo9)
<br>
##### 혹시 바로 적용 안되시는 분은 글 작성하는 부분에서 "엔터"를 한번 쳐주시면 아마 잘 보이실 겁니다....!!

___

제가 샘플로 적용한 타이틀은 이 디자인 인데요,  다른 디자인이 필요하신 분들은 또 스크립트를 살짝 수정하셔야 하는데요... 그게 케이스 마다 조금 달라서 필요하신 분 있으시면 댓글 달아주시면 제가 스크립트를 만들어 드리겠습니다요..!!

뭐... 엄청 많은 분들이 신청해주시진 않겠죠~^^;;

이상이고요..!!!
태풍 아저씨가 지나가고~ 정열적인 화창한씨가 돌아왔네요..!!
다들 더운데 몸관리 잘하시고 남은 하루도 잘잘 보내시길 바랍니다..!!!!

# 건강하세요~~~~ ^^