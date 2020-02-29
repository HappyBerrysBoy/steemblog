---
title: '[kr-dev] Javascript에서 Class형태 정의 방법'
tags:
  - kr
  - kr-dev
  - busy
  - javascript
  - oop
author: happyberrysboy
categories: dev
excerpt: "<img src=\" Unit.js\" />\r\n## 이글은 개발자 분들을 위한 글임을 먼저 밝혀드립니다.  안녕하세요, 해피베리보이입니다.  오늘 야밤에는.. Javascript에서 클래스 형태로 변수를 정의 하는 부분을 포스팅 해보려고합니다. 아시다시피 javascript는 클래스 형태를 따로 제공하지 않습니다. 물론 ES6에서는 제공하고 있지만, 아직 현실에서 열심히 사용되고 있을 Internet ....."
date: 2018-03-03 01:43:12
---

## 이글은 개발자 분들을 위한 글임을 먼저 밝혀드립니다.

안녕하세요, 해피베리보이입니다.

오늘 야밤에는.. Javascript에서 클래스 형태로 변수를 정의 하는 부분을 포스팅 해보려고합니다.
아시다시피 javascript는 클래스 형태를 따로 제공하지 않습니다.
물론 ES6에서는 제공하고 있지만, 아직 현실에서 열심히 사용되고 있을 Internet Explorer 유저들을 무시할 순 없겠지요. 
안전빵으로 아직은 ES5 정도로 맞춰서 개발하는게 좋을 듯 싶습니다.

지금 스팀에 올릴 게임을 하나 개발중인데, 그 소스를 예시로 작성해보도록 하겠습니다.
겸사겸사 공부 및 재미로 하는 부분이라 제가 다시 보기 위해 남기는 부분이기도 합니다.

___

게임에는 보병이나, 기병, 궁병 등이 나올 예정이라서 먼저  Unit.js를 정의해 보았습니다.

Prototype은 클래스의 정의된 속성이나 함수들을 정의해서 사용 할 수 있습니다.
아래와 같이 단순 변수나 function을 이용해서 함수도 할당 할 수가 있지요.
Prototype 내에서의 "this"는 클래스 자체를 가리킵니다.
기본적인 변수들과, 각종 이벤트를 추가 하였습니다.(공격, 데미지 입음, 죽음여부 확인 등)

## Unit.js

```
// var로 선언과 동시에  function을 선언하면 최초 선언되는 부분은 생성자(constructor) 역할을 한다.
// 최초 1회만 실행 된다.
var Unit = function(name, power, life, body, attacktype, issplash, special)｛
    var self = this;       // this는 함수내의 다른 변수에서 사용시 헷갈릴 수 있어 self로 치환한다.
    self.name = name;
    self.power = power;
    self.life = life;
    self.initPower = power;
    self.initLife = life;
    self.body = body;
    self.attacktype = attacktype;
    self.splash = issplash;
    self.special = special;
｝
// Unit의 Prototype 정의
Unit.prototype = ｛
    name:'',                // Unit Name
    power:0.0,              // Unit Power(Attack)
    life:0.0,               // Unit Life(0=dead)
    initPower:0.0,          // Initial Power
    initLife:0.0,           // Init Life
    body:'',                // Unit Type
    attacktype:'',          // Attack Type
    splash:false,           // Splash
    special:'',             // Special Telent Name
    isMagic:false,
    getLife:function()｛
        return this.life;
    ｝,
    getPower:function()｛
        return this.power;
    ｝,
    doAttack:function(target)｛
        target.doDamage(this.power);
        this.doDamage(target.power);
    ｝,
    doDamage:function(dmg)｛
        if(this.life <= dmg)｛
            this.life = 0;
        ｝else｛
            this.life -= dmg;
        ｝
    ｝,
    isDead:function()｛return this.life > 0 ? false:true｝,
    doSpecial:function()｛
        // 특수기능 구현 함수
    ｝
｝
// nodejs용 export
exports = module.exports = Unit;
```

간단히 만들어본 Unit.js를 이용해서 이제 전쟁을 일으켜 봅니다.(~~전쟁이라기엔 너무나 간단하지만요..^^~~)

# War.js
```
var Unit = require('./Unit.js');
// 이름, 공격력, 생명력, 유닛유형(대중소), 공격유형(일반,대형,소형), 스플래시여부, 특수능력을 할당
var footman = new Unit('footman', 1, 2, 'small', 'melee', false, null);
var knight = new Unit('knight', 3, 3, 'medium', 'melee', false, null);
var archer = new Unit('archer', 2, 1, 'small', 'melee', false, null);
// footman이 knight를 공격
footman.doAttack(knight);
/////////////////////////////////
// 공격이 완료 된 후에 죽음 여부 확인
if(footman.isDead())｛
   console.log('Footman is died');
｝
if(knight.isDead())｛
   console.log('Knight is died');
｝
console.log(footman);
console.log(knight);
// 결과 : Footman is died
// ｛ name: 'footman',
      power: 1,
      life: 0,
      initPower: 1,
      initLife: 2,
      body: 'small',
      attacktype: 'melee',
      splash: false,
      special: ''｝
// ｛ name: 'knight',
      power: 3,
      life: 2,
      initPower: 3,
      initLife: 3,
      body: 'medium',
      attacktype: 'melee',
      splash: false,
      special: ''｝
```

- footman, knight, archer를 정의하고 각각의 공격력, 생명력, 기타 특수 능력들을 정의 했습니다.
- 그리고 footman과 knight를 싸움 시켜봤지요.(archer는 구경꾼~)
- footman은 knight에게 1의 공격을 가하여 생명력을 3에서 2로 낮추었고,
- knight는 다시 footman에게 공격을 가하여 생명력을 2에서 0으로 낮추었습니다.
- 결론적으로는 footman이 사망을 하게 되는 결과를 가져옵니다.

___

참고로 ES6를 쓰는 경우 아래와 같이 표현도 가능합니다.

# ES6 Unit.js

```
var Unit = class ｛
    constructor(name, power, life, body, attacktype, issplash, special) ｛
        this.name = name;
        this.power = power;
        this.life = life;
        this.initPower = power;
        this.initLife = life;
        this.body = body;
        this.attacktype = attacktype;
        this.splash = issplash;
        this.special = special;
    ｝
｝;
```

ES6 에서는 class라는 정의가 아예 정해져 버렸죠.
게다가 ES6는 상속까지도 가능해졌죠.
저도 아직은 익숙하지 않지만, 점차적으로 ES6 코딩을 해보려고 생각중에 있습니다.

___

지금까지 게임을 코딩해본건... 대학교 시절 테트리스 이후로는 한번도 없었는데,
뭔가 새로 만들어 보니 갑자기 너무 재미가 있네요~~ ^^

3월 중으로 빡세게 코딩해서 게임을 공개해보도록 할게요~~
저의 기획력과 개발력이 어느정도 먹히는지 시험해 보고 싶습니다..!!!

**다쓰고 저장까지하고 보니 또 사진이 없네요....**
**그냥 먹는사진만 올리니 힘들어 하시는 분들이 있어...**
**오늘은..... 귀밝이술로 마신 와인사진을 하나 짠!!**
**~~부끄럽게 손발이 나왔군요 ^^~~**
![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1520009840/nnjdpmdmlemah7kp4ftw.png)
