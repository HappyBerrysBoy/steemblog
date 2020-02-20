---
title: GraphQL 학습 - 1
tags:
  - sct
  - sct-kr
  - sct-dev
  - bs
  - mini
  - zzan
  - kr-dev
  - dblog
  - palnet
author: happyberrysboy
date: 2020-01-07 20:52:33
---

![](https://cdn.steemitimages.com/DQmQfLngNsvtMszhqdiGXkBjYQquKCRucxTXrNBjVjG1991/image.png)

안녕하세요 햅뽀이입니다.

새해니까!! 올해도 열심히 개발 공부를 하겠다는 목표를 세웠습니다. 일단 Nomad Coders Academy에 있는 무료 강의들 중에 관심 있었던 것들 부터 들어 볼까 합니다.

그 중의 첫번째가 GraphQL입니다.

동영상 강의 자체는 모두 들었고, 실제로 개발하면서 정리하는 시간을 가져보려 합니다.

강의 위치 : https://academy.nomadcoders.co/

![](https://cdn.steemitimages.com/DQmNpg2UGhNibzGLQeTYd922ExvJRja3NBbTGTmWdcNApmP/image.png)

___

### 샘플이자 GraphQL의 거의 모든 것을 대표하는 소스입니다.

```
const GraphQLServer = require("graphql-yoga").GraphQLServer;

const datas = [
    ｛
        id: 0,
        name: "Name1",
        data: "Data1"
    ｝,
    ｛
        id: 1,
        name: "Name2",
        data: "Data2"
    ｝
];

const typeDefs = 
`
type 
       Data ｛    
           id:Int!
           name:String!
           data:String!  
       ｝  

type
   Query ｛
        getData (
           id:Int
        ): [Data]!    
｝`;

const resolvers = ｛
  Query: ｛
    getData: function(_, _a) ｛
      var id = _a.id;

      return datas.filter(function(data) ｛
        return data.id === id;
      ｝);
    ｝
  ｝
｝;

const server = new GraphQLServer(｛ typeDefs: typeDefs, resolvers: resolvers ｝);
server.start(function() ｛
  return console.log("Server is running on localhost:4000");
｝);

```

이 소스에 거의 모든 것이 들어 있습니다.(제가 배운 부분까지는 말이죠!)

- datas : 데이터 리스트(DB로 생각하시면 됩니다.)
- typeDefs : GraphQL에 데이터형태와, 쿼리시 조회 할 수 있는 형태 등을 정의 합니다.(텍스트 방식입니다.)
- resolvers : typeDefs에 정의된 내용을 호출 할 때 resolvers에 정의된 함수를 거쳐서 결과 값을 보내줍니다.
- server : GraphQLServer 인스턴스를 생성하고, 정의된 typeDefs, resolvers를 설정합니다.
- server.start() : GraphQL 서버를 시작합니다.

다 끝!!??

이정도만 해놓고 실행을 해도, 엄청난 결과물을 확인 하실 수 있습니다.

___

##### 서버를 시작하고...

- http://localhost:4000/ 로 접속을 합니다.
- 그러면 아래와 같은 화면(Play Ground)가 나타납니다.
- 그리고 제가 등록한 소스에 정의된 대로 쿼리를 해볼 수 있도록 기능을 제공해줍니다.

![](https://cdn.steemitimages.com/DQmeuNAtsHSi5kQPi4gkVdVL7fiAVY1anKTmzxf951PxSuD/image.png)

##### 조회 문법
```
// 조회 문법
query｛
  getData(id:0)｛
    name
  ｝
｝
```
 
##### 그리고.. 결과물
```
// 결과물
｛
  "data": ｛
    "getData": [
      ｛
        "name": "namename"
      ｝
    ]
  ｝
｝
```


일단 여기까지는 따라와 오셔도 됩니다. 그리고 작성된 소스, 쿼리 문법, 결과물을 분석해 보겠습니다.

#### typeDefs
- 먼저 typeDefs에서, Data를 정의합니다. Data는 3개의 속성을 가집니다. `id, name, data` 이고 각각 `Int, String, String` 로 정의한다는 의미입니다.

- 그리고 Query에서는 조회하는 명령어를 입력하고, 입력 할 수 있는 parameter들, 그리고 리턴 결과 형태를 표시합니다.
- 조회하는 명령어는 **getData**입니다. 그리고 입력 할 수 있는 parameter는 `id, name, data` 세 개가 입력 가능하고 리턴 형태는 `Data` 형태를 가집니다.  Data 형태란 바로 위에 typeDefs에 정의한 그 Data를 말하는 것이지요!!

#### resolvers
- typeDefs에서 정의한 Query 였던 getData를 입력 받으면 실제로 내부적으로 작동하는 함수를 가집니다.
- getData와 Parameter을 받으면 _a 변수로 해당 파라미터를 받을 수 있습니다.
- _a를 통해 전달 받은 Parameter id 값으로, DB로 부터 해당 id값을 가지는 Object를 return 하게 되는 간단한 함수입니다.

#### 조회문법
- 정의된 getData를 입력하고() 안에 Parameter을 입력합니다. 여기서는 id값으로 0을 입력하였습니다.
- 그리고 ｛ name ｝ 부분은 결과물을 보여 줄때 Data Object의 어떤 변수 값만 보여줄 지를 설정할 수 있습니다.
- 현재는 name만 입력을 했지만, ｛name, data｝를 입력하면 결과물에 name, data를 모두 보여주게 됩니다.


___

예전에 @anpigon님이 끝내주는 기술이라고 얼른 배우라고 했는데, 이제서야 배우게 됐네요.
그리고나서 들었던 생각이 ... 왜 이제야 이걸 알았을까?? 였습니다.

정말 직관적이고, 간단하고, 서버 설정도 필요 없습니다.
앞으로는 정말 api 서버는 무!조!건! GraphQL 입니다!!!

### 끝~~~~~~내주는 이 GraphQL..!!!! 한번 써보시지 않겠습니까? ^^