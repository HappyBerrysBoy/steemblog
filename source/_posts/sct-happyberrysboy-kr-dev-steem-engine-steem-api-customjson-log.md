---
title: '[kr-dev] 채굴풀 개발을 위한 Steem Engine / Steem API Custom_JSON Log 분석'
tags:
  - sct
  - sct-ubi
  - jjm
  - kr-dev
  - sctm
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://steemitimages.com/640x0/https:/\" />\r\n/cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)  안녕하세요, 햅뽀이입니다.    SCTM 채굴풀을 만들기 위해서 열심히 개발을 하고 있습니다. 채굴풀의 안정적인 운영을....."
date: 2019-06-25 14:18:57
---

![](https://steemitimages.com/640x0/https://cdn.steemitimages.com/DQmU8hwnAWm29BmczzrLHGfxPhDsUyr8VQwF8UiFdRrFgjY/％EC％83％88％20％ED％8C％8C％EC％9D％BC％202019-02-27％2017.53.44_2.jpg)

안녕하세요, 햅뽀이입니다.



SCTM 채굴풀을 만들기 위해서 열심히 개발을 하고 있습니다. 채굴풀의 안정적인 운영을 위하여 열심히 분석하고 개발한 글에 대해서 간단히 메모겸 포스팅을 합니다. 

### 개발자 분들을 위한 글이니 참고바랍니다.

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

## 필요사항
- 임대자 임대/임대철회 자동 모니터링
- 그에 따른 지분율 계산
- 채굴 결과 확인
- 수익분배

#### 임대/임대철회 자동모니터링
- 사용 API : sscjs(https://api.steem-engine.com/rpc/)
- 사용 함수 : streamFromTo
- Action : delegate
- Symbol : SCTM
- Sender/To 확인
- Amount 확인
- Timestamp 확인

```
ssc.streamFromTo(blockNoFrom, blockNoTo, (err, result) => ｛｝);
// Sample Data
"blockNumber": 12,
	    "refSteemBlockNumber": 25797141,
	    "previousHash": "9389c132270c7335b806a43bd063110fe3868015f96db80470bef2f48f1c2fcb",
	    "timestamp": "2018-09-09T02: 48: 48",
	    "transactions": [
	        ｛
	            "refSteemBlockNumber": 25797141,
	            "transactionId": "b299d24be543cd50369dbc83cf6ce10e2e8abc9b",
	            "sender": "smmarkettoken",
	            "contract": "smmkt",
	            "action": "updateBeneficiaries",
	            "payload": ｛
	                "beneficiaries": [
	                    "harpagon"
	                ],
	                "isSignedWithActiveKey": true
	            ｝,
	            "hash": "ac33d2fcaf2d72477483ab1f2ed4bf3bb077cdb55d5371aa896e8f3fd034e6fd",
	            "logs": "｛｝"
	        ｝
	    ],
	    "hash": "e97e4b9a88b4ac5b8ed5f7806738052d565662eec962a0c0bbd171672a4a54d4",
	    "merkleRoot": "2f1221ae1938bc24f3ed593e8c57ea41882fedc5d31de21da9c9bd613360f3a6"
```


#### 지분율 계산
- 전체 임대량 대비 각자 계정 지분율 계산

#### 채굴결과 확인
- 사용 API : steem js
- 사용 함수 : getBlock
- type : mining
- Symbol : SCT
- Winners : winner
- Amount : claim_token_amount
- Timestamp 확인

```
content:｛
	"symbol":"SCT",
	"type":"mining",
	"N":10,
	"staked_mining_power":257005.6846,
	"winner":["tradingideas","eagleowl","sctm.winners","bongje","corn113","omit","anggreklestari","sonki999","tradingideas","lovelyyeon.sct"],
	"claim_token_amount":13.08,
	"trx_id":"b55862867954e2350be9483a392aa4d01a65e7b5",
	"block_num":34094987,
	"N_accounts":143｝",
	"level":"info",
	"message":"info",
	"timestamp":"2019-06-25 10:36:26"｝
```


#### 수익분배
- 지분율 가져와서 채굴량 대비하여 지분만큼 분배
- custom_json을 이용하여 코인 분배 

![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)

채굴관련하여 필요하신 분은 참고하시면 될것 같습니다.
또는 관련하여 궁금한게 있으시면 댓글 주시면 답글 달아 드리도록 하겠습니다.

여기까지 읽어주셔서 감사합니다.

