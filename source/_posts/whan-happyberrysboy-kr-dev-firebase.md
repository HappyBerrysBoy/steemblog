---
title: '[kr-dev] Firebase 데이터베이스 프로젝트 설정'
tags:
  - whan
  - kr-dev
  - firebase
  - jjm
  - busy
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmbo4bis7WgjdVYdXR9VbzWdzh2aCXw2JFVKfruYNCNV4G/wdt.png)  안녕하세요, 햅뽀이입니다.  오늘은 Firebase의 데이터베이스 설정하는 방법을 함께해보려고합니다.  !]( 원래 이렇게 많은 서비스를 제공하고 있지만, 일단 저는 데이터베이스가 필요 하기 때문에 먼저 데이터베이....."
date: 2019-06-02 15:39:48
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmbo4bis7WgjdVYdXR9VbzWdzh2aCXw2JFVKfruYNCNV4G/wdt.png)

안녕하세요, 햅뽀이입니다.

오늘은 Firebase의 데이터베이스 설정하는 방법을 함께해보려고합니다.

![image.png](https://ipfs.busy.org/ipfs/QmU69NrWnZviCTDGrHh1iRvBrq5fYetvvwboUoksgku7TY)
원래 이렇게 많은 서비스를 제공하고 있지만, 일단 저는 데이터베이스가 필요 하기 때문에 먼저 데이터베이스만 다루어 보려고합니다. 간단한 앱의 DB로는 Fireabase의 데이터베이스가 짱이라던 @anpigon 님의 말을 듣고, 설정을 실제로 해보면서 포스팅을 작성해봅니다.

___

## 1. Firebase 접속 및 프로젝트생성
- 이미 하나 추가를 한 상태에서 캡쳐를 했네요.
- 현재개발중인 Steem Tools의 사용자별 설정을 DB로 저장해놓고 어느 크롬에서도 불러올 수 있도록 개발할 예정입니다.
- steem-extension 으로 프로젝트명을 설정하였습니다.

![image.png](https://ipfs.busy.org/ipfs/QmemkM82PKWf8NmuXGJdzBC2KRBukRXGHNZ8X5nfzF2K8K)

## 2. Firebase Console
- Firebase 콘솔화면입니다.
- 개발도구 뿐만아니라 품질/분석/성장에 대한 부분까지 종합적으로 서비스를 합니다.

![image.png](https://ipfs.busy.org/ipfs/QmUNae4KPPgtdknFnVF91sC2GRd95s2ZPWtJwviZbCVjcL)

## 3. 데이터 베이스 설명
- 데이터베이스는 [Realtime Database](https://firebase.google.com/docs/database?authuser=0) / [Cloud Firestore](https://firebase.google.com/docs/firestore?authuser=0)로 구분됩니다.

 ![image.png](https://ipfs.busy.org/ipfs/QmRsWKfu8Qj2oo9irv9ZGZ6qMTgbpEaMR5hBh8SGJJ8o3u)

- [차이점 설명](https://firebase.google.com/docs/database/rtdb-vs-firestore?authuser=0) 를 참고하시면 차이점을 아실 수 있을 듯 합니다.
- 두가지 DB 모두 No-SQL 기반입니다.
- 그 외에 많은 비교설명이 있는데, 대체로 Cloud Firestore가 진보된 DB라고 설명하고 있습니다.
- 그래서!! Cloud Firestore로 진행해봅니다..!! 최신을 써봐야죠!!

## 4. Web에 Firebase 설정
- 현재 개발중인 Chrome Extension은 웹기반이기 때문에 웹으로 설정합니다.
- [웹 이외의 언어](https://firebase.google.com/docs/firestore/quickstart?authuser=0)는 링크를 참조하시면 됩니다.

```
<script src="https://www.gstatic.com/firebasejs/4.12.1/firebase.js"></script>
<script src="https://www.gstatic.com/firebasejs/4.12.1/firebase-firestore.js"></script>

//  Cloud Firestore 인스턴스를 초기화합니다.
firebase.initializeApp(｛
  apiKey: '### FIREBASE API KEY ###',
  authDomain: '### FIREBASE AUTH DOMAIN ###',
  projectId: '### CLOUD FIRESTORE PROJECT ID ###'
｝);

// Initialize Cloud Firestore through Firebase
var db = firebase.firestore();
```

## 5. Firebase Database 사용법(쓰기)
- Cloud Firestore는 컬렉션에 저장되는 문서에 데이터를 저장합니다. 문서에 데이터를 처음 추가할 때 Cloud Firestore에서 암시적으로 컬렉션과 문서를 만듭니다. 컬렉션이나 문서를 명시적으로 만들 필요가 없습니다.

```
db.collection("users").add(｛
    first: "Ada",
    last: "Lovelace",
    born: 1815
｝)
.then(function(docRef) ｛
    console.log("Document written with ID: ", docRef.id);
｝)
.catch(function(error) ｛
    console.error("Error adding document: ", error);
｝);

```

## 6. Firebase Database 사용법(읽기)
- Cloud Firestore에 추가한 데이터를 빠르게 확인하려면 Firebase 콘솔의 데이터 뷰어를 사용하면 됩니다.

```
db.collection("users").get().then((querySnapshot) => ｛
    querySnapshot.forEach((doc) => ｛
        console.log(`$｛doc.id｝ => $｛doc.data()｝`);
    ｝);
｝);
```

## 7. 저장된 데이터 확인
- 아래와 같이 데이터가 저장되었습니다. DB 설계를 하지 않아도 일단 그냥 들어가고 봅니다.(테스트를 여러번해서 동일 데이터가 여러번 들어갔습니다.)
- 추후 Update/Delete 기능도 확인해볼 예정입니다.

![image.png](https://ipfs.busy.org/ipfs/QmNc4Bx1duLYCdSRWAEAitna5u2Z7DHu6LiuL1oxrAVtWA)


___

생각보다 정리하면서 실행해보려니 오래 걸리네요. 아직 파악해볼 기능이 많은데, 오늘은 여기까지 해야 하겠습니다. 4시간을 공부하면서 정리했네요;;

그럼 남은 주말.. 잘 보내십시오..

읽어주셔서 감사합니다!!

## WHAN DEV TEAM 가즈아!!!