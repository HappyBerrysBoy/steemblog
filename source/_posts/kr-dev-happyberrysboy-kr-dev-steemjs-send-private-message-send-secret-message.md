---
title: '[kr-dev] Steemjs를 이용하여 비밀메세지(send private message, send secret message) 보내기'
tags:
  - kr-dev
  - kr
  - steemjs
  - private
  - busy
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemit.com/kr/@segyepark/5uabay\" />\r\n안녕하세요 해피베리보이입니다.  오늘 steemjs api 스터디를 하다가 비밀메세지 보내는 방법을 알아내어 포스팅을 해보고자 합니다. (열심히 찾아봤는데, 비밀메세지 보내는 방법은 안보이더라고요...)  **코딩이 아닌 일반적으로 비밀메세지를 보내는 방법은 @segyepark 님이 아래와 같이 잘 포스팅 해주셨습니다.**  사용법 및 주의점도 있으니 잘 ....."
date: 2018-02-24 00:10:39
---

안녕하세요 해피베리보이입니다.

오늘 steemjs api 스터디를 하다가 비밀메세지 보내는 방법을 알아내어 포스팅을 해보고자 합니다.
(열심히 찾아봤는데, 비밀메세지 보내는 방법은 안보이더라고요...)

**코딩이 아닌 일반적으로 비밀메세지를 보내는 방법은 @segyepark 님이 아래와 같이 잘 포스팅 해주셨습니다.**

사용법 및 주의점도 있으니 잘 읽어보시면 도움이 됩니다.(**비밀번호 변경시 기존 메세지를 읽을 수 없다 던지 하는 부분은 주의하셔야겠지요..!!**)
https://steemit.com/kr/@segyepark/5uabay

___

**비밀메세지란 것은 메세지 내용이 암호화 되어, 보낸사람과 받는사람만 볼 수 있는 메세지 입니다.**

바로 소스부터 갑니다..

```
var steem = require('steem');

// sender
var from = 'sender id';

// receiver
var to = 'receiver id';

// amount steem or sbd(SBD를 보내지 않고서는 메세지가 가지 않습니다.)
var amount = '0.001 SBD';   // or '0.001 STEEM'

// private message(#을 꼭 넣으셔야 합니다.)
var memo = '#Private Message';

// sender activekey
var activekey = 'sender activekey';

// sender private memokey
var sender_memokey = 'sender private memokey';

// receiver public memokey
var receiver_memokey = 'receive public memokey';

// convert message to private message
var private_message = steem.memo.encode(sender_memokey, receiver_memokey, memo);

// send message and sbd
steem.broadcast.transfer(activekey, from, to, amount, private_message, function(err, result) ｛
  if(err)｛
      console.log(err);
  ｝else｛
      console.log(result);
  ｝
｝);

```

소스에 특별한 설명이 필요 없어 이만 줄이도록 하겠습니다.
기능이 필요하신 분들은 활용해주시면 되겠습니다.
혹시라도 추가로 궁금한 사항이 있으시면 댓글 주세요..!!

아 오늘도 사진이 없네요... 보자.. 조금전에 먹은 라면을..
신라면 + 땡초 + 버섯 + 양파 + 계란입니당 ^^;

![noodle.JPG](https://steemitimages.com/DQmYpmfrCYHSGgvzDMeHvxuB8qHNikydDAEbRGPJmJsMHGh/noodle.JPG)