---
title: NextColony용 API 및 데이터 정리
tags:
  - zzan
  - kr-dev
  - kr
  - jjm
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/ipfs.busy.org/ipfs/Qman2EX2PHQ4YpS5QRttNh6yBApcQQVc3YD2iheeThsdS8)  안녕하세요, 햅뽀이입니다!!  이전부터 즐기던 NextColony를 접으려고 몇 개의 행성도 팔고 했었는데... 갑자기!! 재미로 자동화 봇을 만들다가... 다시 안접게 된(?) 것 같습니다. 참고로 부캐는 꽤나 짱짱하게 잘 컸었는데,....."
date: 2019-07-03 12:44:06
---

![](https://steemitimages.com/640x0/https://ipfs.busy.org/ipfs/Qman2EX2PHQ4YpS5QRttNh6yBApcQQVc3YD2iheeThsdS8)

안녕하세요, 햅뽀이입니다!!

이전부터 즐기던 NextColony를 접으려고 몇 개의 행성도 팔고 했었는데... 갑자기!! 재미로 자동화 봇을 만들다가... 다시 안접게 된(?) 것 같습니다. 참고로 부캐는 꽤나 짱짱하게 잘 컸었는데, 지금 본캐는 아주 그냥... 생... 망계정이지만 ㅠㅠ 아직 생명의 위협을 느껴지지 않아, 탐험은 좀더 즐겨 볼까 합니다. 어짜피 봇이 하는거라서요!! ㅎㅎ

![image.png](https://ipfs.busy.org/ipfs/QmRFMmEfArmoBCgggNuVYuspwYrH5C46LAUsBaAqJJQXYX)
<< 탐사 132번 보냈는데, 행성 하나도 못찾고, 탐험선 11번 터진.. 아주 재수 없는 케이스입니다. >>

자동화 봇을 만들게 되면서 알게된 개발 내용 공유겸 정리 드리려고 합니다. Next Colony 개발하시는 분들에게 도움이 되시길!!

```
// User의 모든 Planets 정보
// sample Data : ｛"misc":｛"total":5077｝,"planets":[｛"id":"P-ZA01QNQO29C","name":"Alpha","posx":-3,"posy":-182,"starter":1｝]｝
`https://nextcolony.io/api/loadplanets?user=$｛account｝`

// 하나의 Planet 정보
// Sample Data : ｛"img":"co_atm_1.png","level_base":3,"level_coal":12,"level_coaldepot":12,"level_copper":12,"level_copperdepot":12,"level_ore":12,"level_oredepot":12,"level_research":3,"level_ship":14,"level_uranium":15,"level_uraniumdepot":12,"planet_bonus":0.0,"planet_corx":-3,"planet_cory":-182,"planet_crts":1555928508,"planet_id":"P-ZA01QNQO29C","planet_name":"Alpha","planet_rarity":"common","planet_type":"earth","shieldcharge_busy":0,"shieldcharged":0,"shieldprotection_busy":0,"startplanet":1,"total_type":4016,"user":"happyberrysboy"｝
`https://nextcolony.io/api/loadplanet?id=$｛planetId｝`

// User의 Skills 정보 
// Sample Data : [｛"busy":1558984189,"coal":1344,"copper":288,"current":14,"name":"shipyard","ore":576,"time":48000,"uranium":156｝,｛"busy":1557335921,"coal":499,"copper":94,"current":12,"name":"oredepot","ore":150,"time":31028,"uranium":52｝,...]
`https://nextcolony.io/api/loadskills?user=$｛account｝`

//  Planet의 자원량 정보
// Sample Data : ｛"coal":323.068,"coaldepot":2880.0,"coalrate":960.0,"copper":470.768,"copperdepot":720.0,"copperrate":240.0,"lastUpdate":1562124006,"ore":221.532,"oredepot":1440.0,"orerate":480.0,"uranium":16.3035,"uraniumdepot":360.0,"uraniumrate":153.0｝
`https://nextcolony.io/api/loadqyt?id=$｛planetId｝`

// Planet의 빌딩 정보
// Sample Data: [｛base:0, busy:1559091080, coal:1344, copper:288, cur_rate:null, current:14, misc:null, name:"shipyard", next_rate:null, ore:576, research:0, skill:14, time:46560, uranium:156｝, ....]
`https://nextcolony.io/api/loadbuildings?id=$｛planetId｝`

// Planet의 Shipyard 정보
// Sample Data : [｛"activated":false,"armor":20,"bullet":0,"busy_until":null,"capacity":160,"class":"Battlecruiser","consumption":0.0038,"cost":｛"coal":576,"copper":144,"ore":288,"time":101323.48,"uranium":72｝,"cur_level":14,"cur_level_skill":14,"laser":0,"longname":"Battlecruiser Tiger","min_level":18,"rocket":8,"shield":36,"skill":null,"speed":2.0,"structure":40,"type":"battlecruiser","variant":0,"variant_name":"rocket"｝,...]
`https://nextcolony.io/api/shipyard?id=$｛planetId｝`

// Planet의 생산력 정보
// Sample Data : coal:｛booster:null, depot:2880, level:12, production:960, safe:0｝, copper....
`https://nextcolony.io/api/loadproduction?id=$｛planetId｝&user=$｛account｝`

```

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

Api와 샘플 데이터가 바로 있어서, 바로 코딩하기 쉬우실 것 같다고 생각이 됩니다!!
참고하십시오!!! 아자아자!! Next Colony는 KR이 접수 하즈아!?