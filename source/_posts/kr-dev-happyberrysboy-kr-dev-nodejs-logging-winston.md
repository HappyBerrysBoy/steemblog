---
title: '[kr-dev][nodejs][logging] winston을 이용한 로그 남기기'
tags:
  - kr-dev
  - kr
  - nodejs
  - logger
  - winston
author: happyberrysboy
categories: dev
excerpt: "<img src=\"\nsteem.js\" />\r\n안녕하세요, 해피베리보이입니다.  오늘은 개발 관련 글을 써보려고 합니다. 를 이용해서 이것저것 해보는 와중에 log를 효과적으로 남길 수 있는 방법이 무엇이 있는가 해서 좀 찾아보다가 \"winton\"이라는 좋은 logging 프로그램이 있어서 사용법을 공유해보고자 합니다.  생각보다 내용이 방대하여, 일단 기초부분에 대해서만 다뤄보도록 하겠습니다.  __....."
date: 2018-01-27 14:42:15
---

안녕하세요, 해피베리보이입니다. 
오늘은 개발 관련 글을 써보려고 합니다.

steem.js를 이용해서 이것저것 해보는 와중에 log를 효과적으로 남길 수 있는 방법이 무엇이 있는가 해서 좀 찾아보다가 "winton"이라는 좋은 logging 프로그램이 있어서 사용법을 공유해보고자 합니다.

생각보다 내용이 방대하여, 일단 기초부분에 대해서만 다뤄보도록 하겠습니다.

___

아래는 github 주소이고요.
https://github.com/winstonjs/winston

___


winston은 먼저 자신만의 logger 인스턴스를 생성해서 사용하는 것을 추천하고 있습니다.
transports 안에 자신의 logger에 필요한 모듈들만 추가가 가능합니다.

지원하는 모듈들은 Console, File ~~심지어 Webhook 까지도 지원합니다.(없어졌나봅니다. 있으면 편했을텐데..)~~ 을 지원합니다.

    const logger = winston.createLogger(｛
        level: 'info',
        format: winston.format.json(),
        transports: [
            // console
            new (winston.transports.Console)(), 
            // file
            new winston.transports.File(｛ filename: 'error.log', level: 'error' ｝),
            new winston.transports.File(｛ filename: 'test.log' ｝)
        ]
    ｝);



Log Level은 기본적으로 아래처럼 설정되어 있습니다.


    const levels = ｛ 
      error: 0, 
      warn: 1, 
      info: 2, 
      verbose: 3, 
      debug: 4, 
      silly: 5 
    ｝

___
위와같이 설정 후 실제로 쓰는 법은 물론 매우 간단합니다.

    logger.log('info', 'information');
    logger.log('error', 'error');
    logger.log('info', 'Log Message', ｛ param1: 'orange', param2:'lemon' ｝);

위와 같이 입력해보시면 transports에 해당되는 부분에 알아서 로그가 쌓이게 됩니다. 
기본적으로 아래 옵션에 따라서 console에 모든 로그가 남게 됩니다.

    new (winston.transports.Console)(), 

___

그리고 아래 옵션으로 인하여 error인 타입의 경우 error.log에 저장되게 됩니다.

    new winston.transports.File(｛ filename: 'error.log', level: 'error' ｝),

___

마지막으로 level 설정이 따로 되지 않았을 경우 모든 로그가 'test.log' 파일에 쌓이게 됩니다.

    new winston.transports.File(｛ filename: 'combined.log' ｝)


___
실행 결과를 보면 아래처럼 json 형태로 저장이 되게 됩니다.

console
![test.PNG](https://steemitimages.com/DQmbDPEGwLdQdqR4naLgPEYc7xnEnpm3ceoA9nTte4quQtk/test.PNG)


test.log 파일
![test_log.PNG](https://steemitimages.com/DQmYS1n2nyDU9B9mgFqjvK627Wnrx8cZXytYRs1L2x88mwd/test_log.PNG)

error.log 파일
![error.PNG](https://steemitimages.com/DQmQ2C95L8Mw1SV1mDEqY2itnMVprdjk9UwxD2cjNG6dzF3/error.PNG)

___

요즘은 워낙 오픈소스로 많은 모듈들이 나와있어서 뭔가 개발해야 할때 먼저 오픈소스를 찾아보게 되네요. 다들 그러시지요?? ㅎㅎ
여기까지 간단히 로그 사용법이고요, 좀더 고급용도로 사용 가능한지 한번 확인 해봐야겠습니다.