---
title: '(3탄, 마지막!!)라즈베리파이로 스트라티스 POS(Stratis Proof of Staking) 하기'
tags:
  - kr-newbie
  - kr
  - coinkorea
  - kr-dev
  - stratis
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemit.com/kr-newbie/@happyberrysboy/pos-staking\" />\r\n안녕하세요, 해피베리입니다.. 3탄이 너무 늦었습니다.. ㅠㅠ   회사 일이 너무 바쁘다 보니.. 시간이 안나 계속 미루다가... 마무리를 지어야 겠다 싶어~ 이시간에 작성해 봅니다..!! ㅠㅠ  먼저 글들 링크는 아래와 같습니다..  1탄 :  2탄 :   3탄에서 일단 끝까지 가볼 생각인데... 일단 한번 시작해 봅니다..!!   먼저 2탄에서는 라즈베....."
date: 2017-08-04 03:22:30
---

안녕하세요, 해피베리입니다.. 3탄이 너무 늦었습니다.. ㅠㅠ 

회사 일이 너무 바쁘다 보니.. 시간이 안나 계속 미루다가...
마무리를 지어야 겠다 싶어~ 이시간에 작성해 봅니다..!! ㅠㅠ

먼저 글들 링크는 아래와 같습니다..

1탄 : https://steemit.com/kr-newbie/@happyberrysboy/pos-staking
2탄 : https://steemit.com/kr-newbie/@happyberrysboy/2-pos-stratis-proof-of-staking

3탄에서 일단 끝까지 가볼 생각인데... 일단 한번 시작해 봅니다..!!


먼저 2탄에서는 라즈베리파이 OS를 설치했었지요..!! 라즈베리 파이 설치 후 기본 설정 값들이 있습니다.
이부분은 사실 "라즈베리파이 OS"설치로 구글에서 검색만 해도 넘쳐흐르도록 많은 글들이 나오긴 하지만..
저도 한번더 간단히 작성해 보도록 하겠습니다.

먼저 2탄 마지막 스샷에 나왔던.. 화면..!!에서 상단에 보시면 "Terminal" 아이콘이 있습니다. 클릭하셔서 터미널을 하나 엽니다.
여기서 부터 Linux 를 좀 오시는 분들은 익숙한 명령어일 테지만, 그렇지 않은 분들은 다소 생소한 감이 많으실겁니다.
뭐.. 일단 돈드는것도 아니고~ 명령어 실패한다고 큰 문제 생기는 것도 아니니(OS재설치 다시 함 하면 되지요~) 제가 알려드린대로 순서대로 한번 입력해 보시면 될겁니다...!!

첫번째!!  라즈비안 기본 설정
`sudo raspi-config` 입력![스크린샷 2017-08-02 오후 12.47.42.png](https://steemitimages.com/DQmZ1Eg1YiHfBt9DiBKG2XdfmnAdwMeXxfzMnJjWehqfdfg/％E1％84％89％E1％85％B3％E1％84％8F％E1％85％B3％E1％84％85％E1％85％B5％E1％86％AB％E1％84％89％E1％85％A3％E1％86％BA％202017-08-02％20％E1％84％8B％E1％85％A9％E1％84％92％E1％85％AE％2012.47.42.png)
그러면 위와 같은 화면이 나옵니다.
여기서 가장먼저 1. "Change User Password"를 선택합니다. 그리고 바로 적용할 Password를 2회 입력합니다.(1회입력 엔터 후 재입력)![스크린샷 2017-08-02 오후 12.48.17.png](https://steemitimages.com/DQmQFaxfD7mtgoDeTmyLoM7FuiiQRAF1divLGP9kMdiaJg9/％E1％84％89％E1％85％B3％E1％84％8F％E1％85％B3％E1％84％85％E1％85％B5％E1％86％AB％E1％84％89％E1％85％A3％E1％86％BA％202017-08-02％20％E1％84％8B％E1％85％A9％E1％84％92％E1％85％AE％2012.48.17.png)
이 비밀번호는 라즈베리파이 OS비밀번호입니다.(윈도우 첨에 켜면 입력하는 비번이라 보시면 됩니다.)

그다음엔  4."Localisation Options"로 들어갑니다.
Time Zone은  Asia => Seoul 을 선택합니다.(스페이스를 누르면 선택이 됩니다.)
Locale은  en_US.ISO-8859, en_US.UTF-8, ko_KR.EUC-KR, ko_KR.UTF-8 을 선택합니다.(스페이스를 누르면 선택이 됩니다.)
Default는 en_US.UTF-8를 선택하시면 됩니다.
타임존은 라즈베리파이 시간을 한국으로 맞추는 것이고, Locale는 라즈베리파이에서 사용될 문자를 선택하는 겁니다.

마지막으로  5. "Interfacing Options"을 선택합니다.
![스크린샷 2017-08-04 오전 2.13.33.png](https://steemitimages.com/DQmRNxy4nmbvQLtmrcfjpQmayPCgwZgvtTiUCcj4FD2BE4r/％E1％84％89％E1％85％B3％E1％84％8F％E1％85％B3％E1％84％85％E1％85％B5％E1％86％AB％E1％84％89％E1％85％A3％E1％86％BA％202017-08-04％20％E1％84％8B％E1％85％A9％E1％84％8C％E1％85％A5％E1％86％AB％202.13.33.png)
P2 "SSH"와 P3 "VNC"를 선택 후 "Enable"로 활성화 시킵니다.
SSH는 추후 라즈베리파이와 원격으로 터미널을 연결 할 수 있는 옵션이고, VNC는 원격 화면 접속을 할 수 있는 옵션입니다.
SSH의 경우 구글에서 "라즈베리파이 SSH"으로 검색하시면 수많은 포스팅들이 존재할것입니다.(요 방식은 개발자나 언어에 익숙하신 분들이 주로 사용하는 방법)
VNC는 비 프로그래머 분들에게 익숙한.. 원격 접속 기능 입니다. 요것도 "라즈베리파이 VNC"로 검색해보시면 무수히 많은... ㅠㅠ 
죄송합니다 제가 이 포스팅에 그부분들은 검색으로 대체하도록 하겠습니다.

아직 갈 길이.. 멀거든요 ㅠㅠ

일단.. 이까지 하면 `sudo raspi-config` 설정은 완료입니다. 저는 바로 다른 작업들을 하긴 했는데.. 대부분의 포스팅을 보면 한번 껏다가 켜라고 하는군요? ㅎㅎ `reboot`를 입력한번 한번 재부팅 해줍니다.

두번째!! 설치 툴 업데이트 && 업그레이드
대체로 간단합니다.
재부팅이 되고나면 다시 "터미널"을 하나 생성해 주시고 다음과 같이 입력하고 기다리시면 됩니다.
`sudo apt-get update && sudo apt-get upgrade`
그러면 아래와 같이 알아서 무언가가 설치되고 업데이트 되게 됩니다.

![스크린샷 2017-08-02 오후 12.51.06.png](https://steemitimages.com/DQmU8drfJNArCmCxwTXwqQgrp8KVEcigwZg7fUAK5ogYyBh/％E1％84％89％E1％85％B3％E1％84％8F％E1％85％B3％E1％84％85％E1％85％B5％E1％86％AB％E1％84％89％E1％85％A3％E1％86％BA％202017-08-02％20％E1％84％8B％E1％85％A9％E1％84％92％E1％85％AE％2012.51.06.png)

세번째!! 방화벽 설치!!
우리의 소중한 재산 암호화폐! 스트라티스!! 보안을 당연히 염두에 두셔야 겠지요.. 방화벽을 설치 하여 특정 IP대역 이외에는 접근 할 수 없도록 설정을 합니다.

먼저 `sudo apt-get install ufw -y` 를 입력하여 방화벽 툴을 설치합니다.
그리고 `hostname -I` 를 입력하면 현재 라즈베리 파이 IP를 확인합니다.(ex : 172.30.1.20)
라즈베리파이마다 IP가 다를 것이므로 본인의 IP를 확인 후 다음과 같이 입력합니다.(예시 처럼 172.30.1.20 인 경우 아래처럼 172.30.1.0 으로 입력하시면 됩니다.)
`sudo ufw enable && sudo ufw allow from 172.30.1.0/24 to any port 22`  -- 동일 대역 SSH 접속을 위한 설정
`sudo ufw enable && sudo ufw allow from 172.30.1.0/24 to any port 5900` -- 동일 대역 VNC 접속을 위한 설정
`sudo ufw deny 16174` -- 설명서에 해커들이 이 port로 접근할 수 있다고 해서 막으라고 되어 있어요~

그리고 `sudo ufw status` 를 입력하시면 조금 전 설정한 값들이 적용 된 것을 확인 하실 수 있습니다.

위와 같이 방화벽을 설정하고 나면, 동일 대역 IP(A.B.C.D)가 있다면 A.B.C가 동일한 IP대역에서만 접근이 가능해집니다. 해킹에 조금이라도 더 안전하게 되겠지요. 혹시 이 설정 후에 VNC가 안된다거나 SSH 접속이 안되거나 하는 경우 접속을 시도하는 컴퓨터의 IP대역을 의심해 보시면 됩니다.(또는 port, 필자가 5900을 안열고 vnc안된다고.. os재설치 했던.. ㅠㅠ vnc 기본 port가 5900입니다.)


네번째!! stratis 소스 빌드
이제부터 명령어들은 항상 "home/pi"경로에서 이루어져야 합니다.
`pwd`를 입력해보시면 현재 경로가 확인됩니다. `cd`명령어로 여기저기 다니신게 아니라면 현재는 "home/pi"가 현재 경로일겁니다.
여기서 아래와 같이 입력합니다. 빌드를 위해 추가로 설치되어야 할 툴들이라고 보시면 됩니다.
`sudo apt-get install -f build-essential git g++ libtool make unzip wget libboost-all-dev libssl-dev libdb++-dev libdb5.3++-dev libdb5.3-dev libminiupnpc-dev libqrencode-dev -y`

매우 길지만.. 뭐 입력하면 알아서 작동합니다.. 혹시 중간중간에 "y/n"같이 묻는경우가 있으면 1초의 지체도 없이 "y"를 입력하시고 엔터키를 사정없이 입력합니다. 
위 명령어 길이에서 유추가 가능 할 수도 있는데.. 이부분 설치하는데 저는 "40분"이 걸렸습니다. 커피한잔, 게임한판, 기타 다른 볼일들을 보시는걸 추천드립니다.

그다음으로 stratis 소스를 다운 받는 단계입니다. 
`git clone https://github.com/stratisproject/stratisX.git`
입력하시면 해당 경로의 "stratisX" 폴더에 소스를 다운 받습니다.. 금방 받아요~~

완료 후 `cd stratisX`를 입력하여 해당 폴더로 들어간 후,  `cd src && make -f makefile.unix` 를 입력합니다.
그러면 stratis 소스 빌드가 시작됩니다.
명령어 짧습니다.. 하지만 저는 1시간 걸렸습니다.. 멀고도 험한 길이네요.. 아까 끊었떤 게임한판 재시작.. 커피한잔더..는 좀... 다른 볼일들을 추가로 보십니다.. ㅋ

빌드가 완료되면 잔여 데이터들을 제거하기 위해 `strip stratisd`를 입력합니다. 바로 완료!!

그리고.. 옵션 설정이긴 한데.. 어느 경로에서든 stratisd 명령어를 입력 할 수 있게 하기 위해 `sudo mv stratisd /usr/bin`를 입력하십니다.


다섯번째!! Increase the Swap File Size(저도 무슨 과정인지 자세히는 모르지만.. 하라고 해서 저도 했습니다..)
`sudo nano /etc/dphys-swapfile` 입력합니다. 아래와 같이 뜹니다.(노란색 배경화면은.. 제가 잠시 맥으로 ssh 접속해서 추가 작성하는거라 좀.. 색깔이 다르지만.. 내용은 동일합니다.)
저는 이미 값을 변경 했지만, "CONF_SWAPSIZE" 값을 보시면 100이던가... 로 처음에 설정되어 있을겁니다. 이 값을 512 or 1024로변경하랍니다. 뭐가 좋은지 몰라도 저는 왠지 큰값이 좋아보여서 1024로 변경했습니다... ㅋ 죄송합니다.. 이해도 못하는게 글써서.. ㅠㅠ

![스크린샷 2017-08-04 오전 2.48.44.png](https://steemitimages.com/DQmcJSUSG5ZB6Vbc9GwijXjM3CSKftXzawSGuPPxw3Xda4F/％E1％84％89％E1％85％B3％E1％84％8F％E1％85％B3％E1％84％85％E1％85％B5％E1％86％AB％E1％84％89％E1％85％A3％E1％86％BA％202017-08-04％20％E1％84％8B％E1％85％A9％E1％84％8C％E1％85％A5％E1％86％AB％202.48.44.png)

설정 완료 후 `sudo service dphys-swapfile restart` 를 입력하여 변경된 값을 적용합니다. 이것도 몇분 걸립니다. 화면에 아무런 반응 없이 시간만 몇분 흐르니.. 너무 조바심 안내셔도 될것 같습니다. 완료되면 다시 입력할 수 있는 부분이 뜹니다..



여섯번째!! stratis-qt(지갑) 설치 및 컴파일

또!! 설치 및 빌드하는데 필요한 툴들이 있답니다. 이번엔 아까보다 더 깁니다.. 명령어가.. 하지만 아까보다 다행히 시간은 짧습니다. 대략 10분 안짝으로 끝났던거 같네요~!! 아래와 같이 입력합니다.(여러줄로 표시되는거 저거 전부다 한줄인겁니다;;)

`sudo apt-get install -f build-essential autoconf automake git g++ libtool make unzip wget qt5-default qt5-qmake qtbase5-dev qtbase5-dev-tools libqt5webkit5 libqt5webkit5-dev libqt5qml5 libqt5quickwidgets5 qml-module-qt-labs-settings qtdeclarative5-dev-tools qttools5-dev-tools libboost-all-dev libssl-dev libdb++-dev libdb5.3++-dev libdb5.3-dev libminiupnpc-dev libqrencode-dev libprotobuf-dev`

완료 후 stratis 지갑 컴파일 작업을 합니다. 현재 경로를 확인 후..(`pwd`) "home/pi"로 맞춰주시고요. 혹시 여기로 오는 방법을 모르신다면.. 터미널 창을 하나더 열면 기본 루트가 여깁니다. "홈/파이" ~ ㅋ
여기서 아래와 같이 입력합니다. 명령어 짧습니다. 시간 졸라 깁니다.. 저는 끝나는 시간을 정확히 캐치하진 못했지만..1시간 40분 후에 완료된걸 확인 할 수 있었습니다. ㅠㅠ 게임 다시 ㄱㄱ 생필품 쇼핑 ㄱㄱ

`cd stratisX;qmake;make;strip stratis-qt`


일곱번째!! 지갑 실행 및 sync 맞추기
일단 여섯번째!! 까지 해서 지갑 설치는 완료 되었습니다.(지갑에서 스테이킹을 할수 있습니다.)
그러면 아래처럼 입력해서 지갑을 실행합니다.
`./stratis-qt` -- 현재 경로 "home/pi/stratisX" 기준..(이전명령어 완료 후라면 현재 여기 경로로 되어 있을겁니다.)

지갑 실행도 어느경로에서 가능 할수 있도록 `sudo cp stratis-qt /usr/local/bin`를 미리 한번 입력해주시는 것도 좋습니다.

지갑이 실행되면.... 대망의 stratis wallet이 모습을 드러내게 됩니다..!!
![스크린샷 2017-08-03 오후 8.58.54.png](https://steemitimages.com/DQmcmfrxiFt9SXfQRCAz3Uz2FpW5XVGXXgVSr1rvPTVdqbd/％E1％84％89％E1％85％B3％E1％84％8F％E1％85％B3％E1％84％85％E1％85％B5％E1％86％AB％E1％84％89％E1％85％A3％E1％86％BA％202017-08-03％20％E1％84％8B％E1％85％A9％E1％84％92％E1％85％AE％208.58.54.png)

0스트라.. 첨에 설치하면 당연히 저렇게 되어 있겠지요.. ㅎㅎ 그리고 out of sync로 현재까지의 블록체인 정보와 싱크를 하기 위한 작업을 시작합니다. 그냥 켜놓으면 싱크 작업이 시작됩니다. 이건 시간이..뭐 그냥 넉넉잡아 12시간 잡으시면 될듯합니다.. 체인이 커질수록 더더 오래 걸리겠지요. 

싱크가 되는 동안 왼쪽에 메뉴들을 몇개 눌러 봅니다.
Receive는 현재 지갑 주소정보, 받은 내역들이 뜨고요
Send는 보낼 수 있는 기능!!
Transactions 는 이 지갑에 들락날락거린 스트라들
Address book는 주소들 등록하는 화면인가 봅니다? 

나머지 POS 하기는 다른분이 이미 스팀잇에 올린부분을 따라 하시면 될듯합니다.
이 링크(https://steemit.com/kr/@sjc333/5kyv2u-pos)를 따라하면 좋을 듯 하네요~ 
이분은 아마 윈도우 버전? 일텐데.. 일단 지갑생긴게 똑같지요?? 사용법도 동일합니다..!!
이 글(https://steemit.com/coinkorea/@tosintosin/pos-how-to-stratis-mining-pos-kr-en)도 좋네요~


여기까지가 라즈베리파이로 스트라티스 POS하기 마무으리!!! 입니다..

앞으로 또 언제 글을 쓸 수 있을까 싶어, 오늘 무리해서라도 일단 글 작성은 완료 했네요;; 3:12분;; 
저도 평소 글쓰기를 즐겨하진 않지만.. 몇 안되는 장문의 포스팅 중 하나인데, 조금 아쉬움이 남기는 합니다.

앞으로 기회 있으면 스팀잇에 좀 더 글을 남겨보도록 할테고요~ 여기까지 읽어주시고.. 실제로 해보신분들!!
꼭 성공하시길 바랍니다!! 안되면 댓글남겨 주시면 보충설명 해드리도록 할게요~~~!!!

마지막으로 현재까지 제가 POS해서 채굴성공한 내역 공개합니다. 이게 날짜가 들쭉 날쭉하고요.. 참고로 마지막 날짜 이후에.. 제 라즈베리파이를.. 조카가 부셔버려서;; 지금 작성하는 글에 캡쳐된 내용들은 재 설치하면서 캡쳐해준 것들입니다.

참고해주시고요.. POS 채굴 성공 하였는지 일일이 라즈베리 파이 화면을 켜서 확인하는건 번거로우므로, 여기서 확인하시면 간단하니 참고바랍니다.

https://chainz.cryptoid.info/strat/address.dws?SV3R9XrRtVhpbB8vsAFpbGwm3tENwnUGe8.htm

뒷부분은 제 지갑 주소이고요.. 뭐 여기로 몇몇 스트라를 전송해주신다던지.. 하시는 분들은 천사인거 같습니다.. ㅋ
여기 웹사이트에서 "search address block..." 되어 있는 부분에 본인 지갑 주소를 입력하면 현재 본인 지갑의 상태를 아실 수 있고, 채굴정보도 확인 하실 수 있습니다.

마지막으로 저의 채굴 정보만 보여드리고.. 이만 저는... 꿈나라로 가도록 하겠습니다.. 
내일 불금인데.. 즐거운 하루 되시고~ 스트라가.. 조금 회복해서 너무기쁩니다.. 스트라가 개당 10만원이 되는 그날까지!!! 화이링!! ㅋ