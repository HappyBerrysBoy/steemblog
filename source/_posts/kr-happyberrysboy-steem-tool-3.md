---
title: '[Steem Tool 3편] 유저 바로가기 기능 추가!! 디자인 변경..!!(안쓰고 못배겨야 하는데 아직 설치 수가 모자름..!! ㅠㅠ)'
tags:
  - kr
  - kr-dev
  - jjangjjangman
  - j42day
  - busy
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy\" />\r\n안녕하세요 해피베리보이입니다..!!  업그레이드 된 기능으로 돌아 왔습니다..!!(아직 HTML이나 Markdown 템플릿 추가 기능은 미개발 상태입니다 ㅠㅠ)  이름도 좀 바꿨습니다..!!  Steem Markdown Design Tool은 좀 한정적인듯 해서.. 그리고 좀 개발하다보니 기타 편한 기능들을 많이 넣어도 될 것 같아서 그냥 **\"Steem ....."
date: 2018-07-12 02:46:30
---

안녕하세요 해피베리보이입니다..!!

업그레이드 된 기능으로 돌아 왔습니다..!!(아직 HTML이나 Markdown 템플릿 추가 기능은 미개발 상태입니다 ㅠㅠ)

이름도 좀 바꿨습니다..!! 
Steem Markdown Design Tool은 좀 한정적인듯 해서.. 그리고 좀 개발하다보니 기타 편한 기능들을 많이 넣어도 될 것 같아서 그냥 **"Steem Tool"**로 변경했습니다.(현재 버전은 1.1.8입니다.)

자 그러면 새로운 기능과 디자인을 살펴 보실까요..!?

**(설치방법은 이전글을 참고 바랍니다.)**
이전 글 : [[Steem Markdown Design Tool 2편] 자기가 원하는 이미지를 마음껏 추가하고 두고두고 편하게 쓰자...!!(안쓰고는 못 배김!! 대문 쓰는 분들 필수!!)
](/@happyberrysboy/steem-markdown-design-tool-2)
<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

## 새로운 기능
<br>
<center><h3>유저 바로가기 기능(User Shortcut, @kibumh 님 요청사항)</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png</center><br>

- **Input User @ID**란에 바로가기 등록을 원하는 유저(@는 넣든 안넣든 상관없음)를 입력하고 **Add** 버튼 클릭(또는 키보드 **엔터키입력**)
- 그러면 아래쪽 박스에 아이디가 등록되고, 해당 아이디를 **클릭**하면 그 유저의 페이지로 바로 이동
- 삭제를 원하는 경우에는 ID를 입력하고 **Del**을 클릭하면 삭제됨
- 미비한 기능으로 존재하지 않는 ID체크가 되지는 않음(크롬앱에 steem.js cdn 추가시 오류발생, 기능 찾아보는중)
![image.png](https://ipfs.busy.org/ipfs/QmUYonecguiDR886MyeFjLKdz8c8b5t5osLgu7tWmrJoxx)

<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

<br><br>
## 변경된 기능
<center><h3>1. 소스 등록시 소스 이름 추가 및 이미지 여부 체크</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png</center><br>

- 이전 버전에서는 단순히 이미지 소스만 추가 하였으나, 앞으로 기능 확장을 고려하면 **이름**을 추가 하는 것이 좋을 듯 하여 기능 추가(HTML 등은 모든 내용을 다 표시 할 수 없어서 이름으로 구분 해야 할 것으로 판단되었음)
- 새로 소스(이미지, HTML, Markdown)을 등록할 때 **Input Name**에 이름을 입력하고, **Input Your Src**에 소스를 입력 한 뒤 이미지 여부를 체크(이미지인 경우 체크된 상태로, gif도 이미지체크)하고  **Add** 클릭
- 아래 처럼 입력하고 **Add**를 클릭하면 
![image.png](https://ipfs.busy.org/ipfs/QmX9CXY5iQ4tk4wMCa87YTLEsG5KctQkErzMKDdVZqKWZs)
- 아래 처럼 이름과 이미지가 등록됨(동일 이름이 있는 경우 등록되지 않음)
![image.png](https://ipfs.busy.org/ipfs/QmY2UiByo539f1R8vqnbHXpdvyXWY9wjoRWUWCujLxWJ5S)
- 글에 추가하는 방법은 이전에 **Add**를 클릭하는 것에서 ![image.png](https://ipfs.busy.org/ipfs/Qma34tqUEq2ts8BS1gDNZkkRhSpYe7ZgKLLw29pCNRHt1w)를 클릭하는 방식으로 변경됨
- **이전에는 글에 바로 소스가 추가가 되었으나, 이번 버전부터 Clipboard로 저장하도록 수정..!! 필요한 위치에 Ctrl + V로 사용가능**
- 소스를 삭제하는 방법은 우측의 ![image.png](https://ipfs.busy.org/ipfs/QmQHp4psDAMkFSFAbg1EPnsf7Y5W1o5kf9ARuSXTFYz5AG) 버튼을 클릭

<br><br>
![](http://cfile23.uf.tistory.com/image/2660F438575273F828DB67)
(위에 등록한 풀 gif..ㅋ)

<br><br>
<center><h3>2. 디자인</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png</center><br>

- 완전 쌩짜 Style Sheet에서 오픈소스 UI Style Sheet를 추가(https://semantic-ui.com/)
- 초딩시절 미술 **가**도 받아봤던 실력으로 얼마나 나아졌겠냐 만은, 나름 고민해서 디자인 옆글(?)!!
![image.png](https://ipfs.busy.org/ipfs/Qmc66xtVH27gwVcQr5eFYg3WLiy9t4Ne3vxUoz12dPjyK3)

<center><h3>3. 소스구조 변경</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png</center><br>
- 이건 개발자 분들 용이라 ㅎㅎ 혹시나 보실분들 보시고 조언좀 부탁드립니다..!! 굽신굽신~(https://github.com/steemhappyberrysboy/steem_design_tool)
- Class 추가 ES6 적극 활용 노력 중

<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)
<br>

현재 사용자 분이 대략 15분으로 확인 되는데요..!! 10000명이 되는 그 순간까지 계속 해봐야겠습니다..!!(요즘은 만이 대세죠?)
![image.png](https://ipfs.busy.org/ipfs/QmYXASdDVm6Ve9kJSG8CpRs8xMbwpFyxCVa1q4hsf6Apuh)

## 사용자수 만명도 가고!! 스팀 만원도 가즈아..!! 
## 모두모두 내일도 잘 보내시고~ 건강한 한주 보내시길 비나이다 비나이다~~!!!