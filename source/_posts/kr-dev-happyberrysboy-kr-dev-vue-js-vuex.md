---
title: '[kr-dev] vue.js 의 핵심 기능!! “VUEX” 정리!!'
tags:
  - kr-dev
  - jjm
  - busy
  - mini
  - yesinfo
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)  안녕하세요, 해피베리보이입니다..!!  오늘도 재미없는 개발글 입니다 ㅠㅠ 그래도 참고 되실분이 있길 바라며..!!! ....."
date: 2019-04-08 07:55:54
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)

안녕하세요, 해피베리보이입니다..!!

오늘도 재미없는 개발글 입니다 ㅠㅠ 그래도 참고 되실분이 있길 바라며..!!!

지금 vue.js의 vuex 부분을 공부하는 중인데, 정리가 필요한 시점이 와서!! 스팀을 켜봅니다.
이게 React에서는 Redux와 비슷합니다!!! Vue나 React가 구조가 비슷해서 여기까지 공부하면 React도 비교적 쉽게 적응이 가능할 거라 믿어 의심을 조금만 해봅니다. ㅎ

Vuex!! 시작!!

___

#### 1. vuex 란?
- 앱의 상태와 관리, 패턴을 지원하는 라이브러리
- 앱 내부의 모든 컴포넌트들이 공유하는 집중화된 상태 정보 저장소
- 상태 데이터는 전역에서 store 객체를 통해서 관리

#### 2. Vuex의 3가지 영역과 헬퍼 메서드
- state : 데이터 영역
- mutation : state를 변경하는 영역(동기로 작동, state를 변수로 접근하여 바로 변경을 하면 추적이 어려우므로 mutation을 이용하여 state를 관리)
- action : 비동기 함수도 호출 가능하고, 처리 후 commit 명령어로 state 변경 가능(commit 명령어로 mutation 호출)
- helper methods : mapState, mapMutations, mapGetters, mapActions

#### 3. helper methods 사용 예제

```
import ｛mapState, mapMutations, mapGatters, mapActions｝ from 'vuex'

export default｛
   name:'Test',
   computed:｛
      mapState(['data', 'list']),
      mapGetters:(['partialData', 'filteredData'])
   ｝,
   ...mapMutations(['mutation1', 'mutation2']),
   methods: ｛
       ...mapActions([
            'action1', 'action2'
       ]),
       ...mapActions(｛
         action1 : 'doAction' // action1 함수를 doAction으로 매핑
       ｝)
  ｝
｝
```

#### 4. helper method, mapStates, mapMutations
- mapStates : store에 정의된 state을 필요한 만큼 나열하는 형태로 설정
- mapMutations : store에 정의된 mutation함수들을 나열하는 형태로  설정

```
computed:｛
   mapState(['data', 'list'])
｝,
...mapMutations(['mutation1', 'mutation2']),
```

#### 5. helper method, mapGetters
- store의 computed 속성(store에서 계산이 되어 있으면 편한 부분을 미리 설정하여 다른 컴포넌트에서 사용 가능)
(현재 프로젝트에 적용할 부분이 많이 보인다..!!)

#### 6. mapActions
- store의 actions들을 나열하는 형태로 설정

___

아.. 좀더 정리가 잘 될 줄 알았는데.. 일단 개념 정도와 저만 조금 알아 보기 쉽게.. 혹은 vue를 좀 아시는 분들이 보실 수 있는 정도로 밖에 정리가 안되었군요..

좀더 이해를 위해서 데이터를 넣자니 너무 커져서 일단 이정도로 정리가 될 듯합니다.
현재 프로젝트에 꼭 들어가야하고, 중요한 부분이기에 한번 읽고 두번읽고 세번읽으면서 정리하는 중이네요..!!

잘 써지길 바라며..!!! 

모두들 평안한 밤 되시길 바라고 또 바랍니다!!!