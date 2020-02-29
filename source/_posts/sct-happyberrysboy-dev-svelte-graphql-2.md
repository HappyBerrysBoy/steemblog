---
title: '[DEV] SVELTE + GraphQL을 이용하여 웹서비스 개발하기 - 2'
tags:
  - sct
  - sct-kr
  - sct-freeboard
  - s
  - union
  - mini
  - zzan
  - dblog
  - palnet
  - kr-dev
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://cdn.steemitimages.com/DQmTrDZQc777cBrg9Vf5GyoTh1kohNAAymUpUcKj9mYhGWz/image.png\" />\r\n  안녕하세요, 햅뽀이입니다.  오늘은 svelte에 대해서 더 깊이 깊이 파보려고 열심히 이것저것을 뒤져보며 실제로 프로젝트도 2개나 만들어서 테스트를 해보았습니다....만.... 아직 큰 프로젝트를 하기에는 시기상조 인듯 합니다.  이유는 크게 3가지 입니다.  ### 1. React의 redux, Vue의 vuex에 해당하는 \"sapper\"가 아직 버....."
date: 2020-02-05 23:16:51
---

![](https://cdn.steemitimages.com/DQmTrDZQc777cBrg9Vf5GyoTh1kohNAAymUpUcKj9mYhGWz/image.png)

안녕하세요, 햅뽀이입니다.

오늘은 svelte에 대해서 더 깊이 깊이 파보려고 열심히 이것저것을 뒤져보며 실제로 프로젝트도 2개나 만들어서 테스트를 해보았습니다....만.... 아직 큰 프로젝트를 하기에는 시기상조 인듯 합니다.

이유는 크게 3가지 입니다.

### 1. React의 redux, Vue의 vuex에 해당하는 "sapper"가 아직 버전 1.0이 안된다.
- 제가 사용해보기 위해 먼저 프로젝트를 설치하고 이것저것을 살펴보았습니다.
- 아직까지는 너무 복잡한 구조로 되어 있습니다. 원래 간단하다고 해서 시작한 것이었는데, 아직 sapper는 정리가 많이 안된 느낌이 너무 강했습니다.
- 문서에도 아래와 같이 나와 있습니다.(아직 진행중!!)

> Sapper is in early development, and some things may change before we hit version 1.0. This document is a work-in-progress. If you get stuck, reach out for help in the .
See the  for help upgrading from older versions.

### 2. ui frameowrk가 너무 적다.
- 웹프로그램을 하려면 또 쓸만한 Components가 많아야 합니다.
- 기존에 사용하던 Bootstrap이나 Jquery를 연동하여 간단한 컴포넌트들을 사용 할 수도 있지만, 요즘은 React, Vue 등에 최적화된 오픈소스 UI Framework들이 많이 있습니다.
- Jquery를 적용해서 UI쪽만 활용해볼까 생각도 하고 있긴 합니다.
- 하지만 아직은 오로지 [이 사이트](https://sveltematerialui.com/)밖에는 보이지 않습니다.(그것도 아주 부실한..)

### 3. 레퍼런스 역시 너무 적다.
- 개발자는 역시 모르면 구글링입니다.
- 하지만 정보가 너무 없습니다. ㅠㅠ 
- React, Vue는 정말 넘치고 넘쳐 너무나 많은 자료를 자랑하는 반면에 아직 Svelte는 많이 부족하네요.

##### 그!래!서! 아직은 시기상조로 판단하였습니다....만!!
그래도 칼을 빼들었으니, 무시라도 잘라보기 위해서 간단한 Static 페이지로 대체를 해보려고 합니다.

___

### 프로젝트명은..!!! 이름하여... 영어 문장 저장하기 및 랜덤하게 저장된 문장을 출력하여 영어문장 외워보기
입니다.

현재 아시는 분은 아시겠지만, 제가 또 열심히 영어공부를 하는 중 아니겠습니까.

그래서 이러한 프로그램을 만들어보려고 합니다.

___

### 오늘은 간단히..
프로젝트를 생성하고 Header 부분과 Body부분을 간단히 만들어 보는 과정을 하도록 하겠습니다.
먼저 Svelte입니다.

___
### 프로젝트 생성

##### 프로젝트생성
- 아래 스크립트를 순서대로 실행하시면 됩니다.
```
npx degit sveltejs/template my-svelte-project
# or download and extract 
cd my-svelte-project

npm install
npm run dev
```
- 그리고 http://localhost:5000/ 으로 접속을 해보면 아래와 같은 화면이 뿅!!
![](https://cdn.steemitimages.com/DQmQHoazFjjyWk5qvptRsZYAuf9FNLaXvZDpP3o45yEjbCh/image.png)

- 프로젝트 폴더구조는 아래와 같습니다.
![](https://cdn.steemitimages.com/DQmY7rJZLnQ7zJRt2L6CkCYpD2QCSDSHvxyJEZaqAqpWFB5/image.png)

- Vue와 유사하게, src/main.js가 메인이 되고, App.svelte가 시작페이지로 연동되어 있습니다.(물론 바꿀수도 있습니다.)

___

### body 넣기

##### App.svelte
- 하나의 svelte 파일안에 web의 3대요소, html, script, css가 모두 들어가고, 모두다 이 파일 안에서 한정되게 작동됩니다.
- <h1> 엘리멘트 안에 ｛name｝이라는 바인딩 함수를 입력할 수 있는데, 이 변수는 script에서 선언한 그 name 변수를 바인딩 하게 됩니다.
![](https://cdn.steemitimages.com/DQmTWcngGYz72LQ2B939e9Sjkz6R8v3TkTZj2yNRq2t95HC/image.png)

##### main.js
- App.svelte를 import하고 target으로 document.body를 지목합니다.
- 그리고 App.svelte에서 export한 변수 name에 "world"라는 값을 넣습니다.

![](https://cdn.steemitimages.com/DQmet9VRbrXRbB327znLzbYQWe7cfQZK6C6qyD5tm3wu7Vz/image.png)

___

### Header 넣기

##### Header.svelte를 만들어줍니다.
- 별다른 기능은 없고, 파란색 긴 bar를 만드는 소스입니다.
![](https://cdn.steemitimages.com/DQmYTwkbLdepojPQsyyag7adsfGjfbPPoxJNtyXjkydH2ao/image.png)

##### App.svelte에 Header값 import
- 이제 다시 App.svelte로 돌아와 조금전에 만든 Header를 import합니다.
- 그리고 아래쪽에 Header을 선언만 해주면!!!! Header.svelte에서 입력한 값이 그자리에 그대로 들어가게됩니다.
![](https://cdn.steemitimages.com/DQmefLMzYfDsgRmovYgnptAXDkSNq7S1GjZCgkECFD3yQGS/image.png)
![](https://cdn.steemitimages.com/DQmZDzCZ1MmN6uR2mNszua4xp6BUy18yUyynJGYVXUShkkZ/image.png)

##### 결과화면
- 위에는 없었던 상단bar가 추가가 되었습니다.
![](https://cdn.steemitimages.com/DQmZPwqZ71r5QqA26vEmSkgW5rju1miMhcZSaMjCdRE5ZYo/image.png)


오늘은 여기까지!!! 다음소스에서는 조금더 기능들을 추가해보도록 하겠습니다.
평안한밤 되십시오!!