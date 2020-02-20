---
title: '[DEV] SVELTE + GraphQL을 이용하여 웹서비스 개발하기 - 3'
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
date: 2020-02-06 11:40:30
---

안녕하세요, 햅뽀이입니다.

어제에 이어 svelte 조금더 진행해봅니다.
아직 GraphQL까지는 안들어 갔고, Svelte로 화면 개발부분입니다.

오늘은 영어문장입력 텍스트박스, 해석 텍스트박스, 추가하는 버튼과 결과를 테이블 형태로 보여주는 부분을 하겠습니다.

___

### 영어문장입력 텍스트박스(InputSentense.svelte 파일 생성)
- 전체 소스를 먼저 공개하고, 설명하는 방식으로 하겠습니다.
- 먼저 textbox에 binding 될 변수, sentense, translated 를 선언합니다.
![](https://cdn.steemitimages.com/DQmUJgdEZ9XLqv1eiMEKLSRxXdS83NgDmDZajHtmaegYkQN/image.png)
- 그리고 이를 이용하여 하단에 input 엘리멘트를 두개 추가합니다. 보시면 bind:value 안에 위에서 선언한 변수가 입력되어 있음을 알 수 있습니다.
- 나머지 부분은 그냥 텍스트박스를 꾸며주기 위한 부분들로 이루어져 있습니다.
![](https://cdn.steemitimages.com/DQmZUK6krgfjS9xtN3gZqd8LaErjy3dz7ZFGmTSMT6YdjTJ/image.png)
- 텍스트박스 하단에는 저장할 수 있는 버튼을 둡니다.
![](https://cdn.steemitimages.com/DQmcrQBgXKwWStMWKZEzycHJvaX8gvJoSvLbZGFrQgyBxju/image.png)
- 버튼 클릭시 발생할 이벤트를 "saveSentense"로 지정합니다.
![](https://cdn.steemitimages.com/DQmaAysKoZWBYyH4WRS3Bd245f7Dn5aVayg2jSxntN8Jbaz/image.png)
- 저장 버튼 클릭시 saveSentense를 호출하는데 이때 내부적으로 문장과, 해석부분을 sentenseDB로 저장을 하고 "dispatch"명령어로 "db"라는 이벤트를 forwarding 처리합니다.
- forwarding 된 이벤트는 이 파일을 import 하는 곳에서 구현하면 됩니다.
- 완성된 화면은 아래와 같습니다.
![](https://cdn.steemitimages.com/DQmPdfgrqEhegnxx7j7r8jZc2NgfKfpeZeNiseytjaAv4d6/image.png)
```
<script>
  import ｛ createEventDispatcher ｝ from "svelte";

  const dispatch = createEventDispatcher();
  let sentense = "";
  let translated = "";
  export let sentenseDB = [];

  function saveSentense() ｛
    sentenseDB.push(｛ sentense: sentense, translated: translated ｝);
    dispatch("db", sentenseDB);
    // console.log(sentenseDB);
    sentense = "";
    translated = "";
  ｝
</script>

<style>
  .txtbox ｛
    width: 60％;
    color: green;
  ｝
</style>

<input
  bind:value=｛sentense｝
  class="txtbox"
  type="text"
  placeholder="Input sentense for saving"
  value="" />
<input
  bind:value=｛translated｝
  class="txtbox"
  type="text"
  placeholder="Input translated sentense"
  value="" />
<br />
<button class="ui primary button" on:click=｛saveSentense｝>Save Sentense</button>

```

___

### 입력된 데이터를 테이블형태로 표시(SentenseTable.svelte 파일 생성)
- 먼저 테이블 html을 먼저 작성합니다.
- 여기서 ｛#each list as item｝ ｛/each｝ 부분은 svelte만의 문법으로 반복문을 실행할 수 있게 됩니다.
![](https://cdn.steemitimages.com/DQmax61LccJboCkJDYaHhv1537iU4cEosaDwGRhnGSVdFBj/image.png)
- 그리고 문장을 입력하는 파일 InputSentense.svelte를 import 합니다.
![](https://cdn.steemitimages.com/DQmak36psBoQynJdGL1dMEVBdEPsAoKHAGu5buc1M7zbTnt/image.png)
- import 받은 InputSentense를 하단에 선언을 해주고, on:db 명령어로 forwarding 된 이벤트 db를 consoleDB라는 함수를 바인딩합니다.
![](https://cdn.steemitimages.com/DQmfYASsXW81KbMrGroYfnCYkZK4y4TnFk6g7qBPdfBg73w/image.png)
- consoleDB에서는 list Array에 InputSentense.svelte로 부터 건내받은 sentenseDB 배열을 정의합니다.
![](https://cdn.steemitimages.com/DQmbDeisa5rEYdW4s6cD8jN16DD2h14xnR1ZUQNHLLh3BWm/image.png)
- 여기서 list에 값이 바인딩 되면, 제일 처음 반복문에서 선언했던 곳이 작동하면서 받은 메세지 수량만큼 테이블 리스트를 만듭니다.
- 이런식으로 표시가 됩니다.
![](https://cdn.steemitimages.com/DQmNtMNiaCkUhsmBQmU7Zq38cH4i3nr9pXKUV6K3xGmNuDz/image.png)
- 제일 우측 칼럼 func는 삭제 기능을 구현할 예정으로 다음 시간에 계속할 예정입니다.


```
<script>
  import InputSentense from "./InputSentense.svelte";

  export let list = [];

  function consoleDB(e) ｛
    console.log(e.detail);
    list = e.detail;
  ｝
</script>

<style>
  .ui.container ｛
    margin-top: 3％;
  ｝
  .table ｛
    width: 100％;
    text-align: center;
  ｝
</style>

<InputSentense on:db=｛consoleDB｝ />

<div class="ui container">
  <table class="ui celled table">
    <tr>
      <th>Sentense</th>
      <th>Translated</th>
      <th>Func</th>
    </tr>
    ｛#each list as item｝
      <tr>
        <td>｛item.sentense｝</td>
        <td>｛item.translated｝</td>
        <td>
          <button class="ui orance button">Delete</button>
        </td>
      </tr>
    ｛/each｝
  </table>
</div>

```

___

### App.svelte에 표시
- 가장 마지막으로 Main View인 App.svelte에 SentenseTable.svelte를 선언하고 호출하면 완료!!

![](https://cdn.steemitimages.com/DQmcZ2o13mrP2ggsQKXT6TzpQTFsWiK5JYnhAueQmqqHQGh/image.png)
![](https://cdn.steemitimages.com/DQmPJMWALHYT4iTU9JDLQgi6dKA42ewmstwbn6AEVdyp3Cx/image.png)

___

쉽게 설명하기가 너무 어렵습니다. ㅠㅠㅠㅠ
어느정도 개발에 대해서 아시는 분들이 봐주실만한 내용이고, 혹 모르는 내용 있으면 댓글 주십시오.

감사합니다!!