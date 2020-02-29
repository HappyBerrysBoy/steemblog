---
title: 아직은 자동화 채굴풀 개발이 거의 불가능!! 그리고 뜻밖의 재미발견!?
tags:
  - sct
  - aaa
  - whan
  - sct-ubi
  - jjm
author: happyberrysboy
categories: game
excerpt: "<img src=\"https://cdn.steemitimages.com/DQmR28gvsfQU2YgnTgW1VmcMUCSRjuaoUfbFgYL179wVCAJ/image.png\" />\r\n  안녕하세요. 햅뽀이입니다.  새로운 대문을 만들어 주신 @anpigon 님께 무한한 감사드립니다. 벌써 2개 째군요. ㅎㅎ   채굴풀 관련해서 개발중인데, 어느정도 되긴 했는데, 제일 중요한 현재 임대중인 유저들의 정보를 얻기가 쉽지 않습니다. ㅠㅠ 관련 API에 누구한테 얼마나 빌려줬다, 누구한테서 얼마나 들어왔다 이런 정보가 필요한데, 수량만 나오고....."
date: 2019-06-27 15:09:30
---

![](https://cdn.steemitimages.com/DQmR28gvsfQU2YgnTgW1VmcMUCSRjuaoUfbFgYL179wVCAJ/image.png)

안녕하세요. 햅뽀이입니다.

새로운 대문을 만들어 주신 @anpigon 님께 무한한 감사드립니다. 벌써 2개 째군요. ㅎㅎ


채굴풀 관련해서 개발중인데, 어느정도 되긴 했는데, 제일 중요한 현재 임대중인 유저들의 정보를 얻기가 쉽지 않습니다. ㅠㅠ 관련 API에 누구한테 얼마나 빌려줬다, 누구한테서 얼마나 들어왔다 이런 정보가 필요한데, 수량만 나오고 To Account 정보가 없습니다. 아직..

물론 모든 블럭을 까서 Database로 저장해서 관리해도 못할 건 없지만, 거기에 들어가는 개발시간이 적지않은데다, 스팀엔진측에서 그냥 API에 해당 정보를 제공해버리면 거기에 들어가는 개발시간이 모두 도루묵이 되는 상황이라서요. 게다가 정확성도, 블록 뒤져서 제가 관리하는 것보다는 스팀엔진측에서 제공해주는 것이 더 정확하기도 하지요. 그래서 해당 API에 임대 세부정보가 나오기 전까지는 자동채굴분배 봇은 보류하는 것이 맞을 것 같습니다. 아마 다른 개발자 분들도 그리 생각하고 있을 듯 하네요.

<< 임대준 계정 API >>
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/3uSEr3LN-image.png)
#####  나간내용은 있지만, 누구에게 나갔다는 말이 없어요!! 

<< 임대받은 계정 API >>
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/pAaO79UA-image.png)
##### 받은 수량은 있지만, 누구에게 받았다는 내용이 없어요!!

그래서 일단 여기까지하고 나중에 해당 내용이 들어 올것이라고 예상하고 그 뒷단을 준비하고 있습니다.

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

#### 그러다가... 다른 곳에서 재미난 것을 찾았습니다!!

Steem API Custom Json 내용을 분석하다보니, 다른 Dapp들의 정보들도 같이 많이 수집이 되더군요. 최근에 y-o-u-t-h-m-e 님께 NextColony 행성을 모두다 넘겨드려서 이제 안하려고 했는데, 해당 로그들이 수집되어서 잠깐 좀더 살펴봤습니다. 

원래 두개의 NextColony 계정을 돌렸었는데, 하나는 너무 이래저래 위치도 상황도 안좋아서 그냥 안하고 있던 걸로 테스트를 해봤어요. 일단 두가지만 해보긴 했는데 잘되네요? 조금 더 연구하면 봇으로 진화 할 수도 있을 것 같긴 합니다.

무슨 말인고하니.. 대략 아래 그림 처럼 프로그램 명령어로 게임에서 실제로 보낸 것 처럼 실행 시킬 수 있다는 내용이지요. 

위 명령어는 전투선을 만들 수 있는 내용이고, 아래 내용은 갤럭시 탐사에 대한 명령어입니다.
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/BATEhZ75-image.png)

### 명령어를 실행해보니, 요렇게 뿅!! 탐사선이 만들어 지기 시작했고요~
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/2NWSHdZv-image.png)

### 요렇게 뿅!! 탐사도 시작했습니다.
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/Aa7cPGzE-image.png)

### Mission에서도 아래처럼 잘 보이고요~(zzings 님에게 탐사선들이 잘 가고 있군요~)
![image.png](https://files.steempeak.com/file/steempeak/happyberrysboy/75grkOPU-image.png)

으흠.. 이거!!! 좀더 연구하면 자동화가 확실히 될것 같긴한데... 시간이 문제입니다. 그리고 제 건강도...

요즘 개발하고싶은건 정말로 정말로 너무나 많은데, 회사업무 + 육아를 모두 하다보니, 시간이 너무 안납니다. 그나마 밤에 시작해서 새벽까지하는데 몇 주정도 그렇게 했더니, 요즘 가끔 머리가 띵~~합니다. 잠이 너무 부족해서 몸에서 신호를 주는 것 같네요. ㅠㅠㅠㅠ 아직도 더 해야하는데!! ㅠㅠ

그래서........ 이제는 밤에는 일단 자고.. 새벽에 잠이 깨어나면 개발을 하고.. 그게 안되면 어떻하지.. 그게 안되면.... 주에 1, 2일 정도만 새벽까지 하던지 해야겠네요..

아무튼.. 여기까지 읽어 주셔서 정말감사합니다.

게임에서 자동봇 같은거 궁금한거 있으시면 물어보세요~ 나도 할 수 있다!! 게임 자동봇 개발편!!! 을 연재할지도요.. ㅋㅋ

그럼 오늘도 즐거운 하루 되시길 바랍니다!!!