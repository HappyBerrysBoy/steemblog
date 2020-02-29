---
title: '[kr-dev] Vue.js 기초!! 간단한 Directives !!'
tags:
  - kr-dev
  - jjm
  - busy
  - mini
  - yesinfo
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)  안녕하세요..! 해피베리보이입니다..!!  요즘 아주 그냥 개발에 불타오릅니다. 개발 포스팅갑니다..!!  ___  오....."
date: 2019-04-04 20:28:39
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)

안녕하세요..! 해피베리보이입니다..!!

요즘 아주 그냥 개발에 불타오릅니다. 개발 포스팅갑니다..!!

___

오늘은 좀 기초지만 정리해놓은 것들이 있어 directives 관련 하여 작성해봅니다.

#### 1. v-text, v-html

- v-text는 변수에 할당된 값을 그대로 보여준다.(Html 태그가 있을 경우 그대로 텍스트로 표시)
- v-html은 변수에 HTML 태그들이 있는 경우 적용된 화면이 나타난다.
- 언뜻보면 v-html이 적용되어 더 좋을 것 같아 보이지만, XSS(Cross Site Scripting)에 취약할 수 있다.(태그안에 <script>로 스크립트 작성이 가능하기 때문이다.)

```
<h1 v-text="Test1"></h1>
<h1 v-html="Test1"></h1>
```

#### 2. v-bind

- html element의 속성들(attributes)을 바인딩 하기 위해 사용
- v-bind는 생략하고 바로 :src 라고 작성하는 것도 가능하다.

```
<img v-bind:src="image_url" />
```

#### 3. v-model

- 양방향 데이터 바인딩이 필요한 경우 사용된다. 화면에서 변경한 값이 내부 변수에 값을 변경시켜 바로 반영이 된다.
- Vue 객체의 data와 mapping 하여 사용한다.
- checkbox나 select에서 배열 정보로 받을 수도 있다.(체크된 모든 값을 배열로 받는다.)
```
<input type="checkbox" v-model="cards" value="1" />
<input type="checkbox" v-model="cards" value="2" />
<input type="checkbox" v-model="cards" value="3" />
<input type="checkbox" v-model="cards" value="4" />
<input type="checkbox" v-model="cards" value="5" />

<input type="text" v-text="cards" />
```

#### 4. v-show
- 조건에 만족하는 경우 화면에 표시한다.
- 실제로 렌더링은 한 후에 display만 none으로 처리한다.
```
<img :src="image_url" v-show="true" />
```

#### 5. v-if, v-else-if, v-else
- 코딩에 제일 많이 사용되는 것 if문이다!!
- v-show와 마찬가지로 조건에 만족하는 경우 반영된다.
```
<img :src="image1" v-if="val <= 0" />
<img :src="image2" v-else-if="val == 0" />
<img :src="image3" v-if="val > 0" />
```

#### 6. v-for
- 위의 if랑 마찬가지로 가장 많이 쓰이는 구문!!
- 딱 봐도 반복문이다!!
```
<table>
   <tr v-for="data in datas">
      <td>｛｛data.name｝｝</td>
      <td>｛｛data.value｝｝</td>
   </tr>
</table>
```

___


가장 많이 사용되는 것들을 소개하였습니다..!!!
오늘은 여기까지!!! 감사합니다!! 