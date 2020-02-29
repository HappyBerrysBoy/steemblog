---
title: '@otac님 단타를 위한 업비트 화면 위치 설정 스크립트 2탄..!!'
tags:
  - kr
  - kr-dev
  - otac
  - coinkorea
  - busy
author: happyberrysboy
categories: dev
excerpt: "<img src=\"[image.png\" />\r\n안녕하세요 해피베리 보이입니다.   지난글 : [@otac님 단타를 위한 업비트 화면 위치 설정 스크립트](/@happyberrysboy/otac)  지난 글에서 @nhj12311 님의 댓글을 보고 현재 체결되고 있는 체결량을 보는게 도움이 될거라는 생각이 들어서 한번 또 만들어 봤어요.  ##### 현재 실제로 체결되고 있는 매수/매도량 합계 표시와 비율....."
date: 2018-05-10 13:29:15
---

안녕하세요 해피베리 보이입니다. 

지난글 : [@otac님 단타를 위한 업비트 화면 위치 설정 스크립트](/@happyberrysboy/otac)

지난 글에서 @nhj12311 님의 댓글을 보고 현재 체결되고 있는 체결량을 보는게 도움이 될거라는 생각이 들어서 한번 또 만들어 봤어요.

##### 현재 실제로 체결되고 있는 매수/매도량 합계 표시와 비율표시입니다.

___

먼저 완성된 모습은 아래처럼 화면 상단에 떠다니게 만들었습니다.
![image.png](https://gateway.ipfs.io/ipfs/QmSQF8PiDnkUGigTz1PRRftQFr3PH5qf9Ay955542rY1Cw)

근데 지금 글을 쓰는시점에 생각해보니... 왜... 제가 이걸 떠다니게 했는지 잘 모르겠군요.. ㅠㅠ
그냥 체결정보 상단이나, 호가창 상단에 넣었어도 됐을텐데 말이죠..
다음번에는 거기로 올려 놓도록 할게요~ ㅠㅠ

___

## 사용법 1. 스크립트를 개발자 console에서 바로 입력
개발자 콘솔은 지난 글에서 활성화 하는법을 알려드렸지요..
거기에 이 명령어를 넣으시면 바로 작동을 합니다.
아래스크립트를 복사 + 붙여넣기를 하시면 위의 최종 화면처럼 적용되도록 하였습니다.

```

// 체결창 호가창 옆으로 옮기는 스크립트 
// 매수/매도 화면을 아래로 내림
$('.mainB .ty01 .halfB .rightB').wrap('<article></article>'); 
// 체결창을 호가창 옆으로 옮기기 위한 디자인 작업
$('.mainB .ty01 .tabB').wrap('<div class="rightB"></div>');
// 체결창을 호가창 오른쪽으로 옮기는 명령어
$('.mainB .ty01 .rightB:eq(3)').insertAfter('.mainB .ty01 .halfB .leftB');
// 체결창 백그라운드를 흰색으로
$('.mainB .ty01 .halfB .rightB:eq(1)').css('background-color','#fff');
// 호가창 사이즈를 한눈에 볼 수 있도록 사이즈 수정
$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB').css('height', '900px');
$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB div').css('height', '900px');
// 체결창 사이즈를 호가창과 동일하게 사이즈 수정
$('.askpriceB .scrollB').css('height', '900px');
$('.askpriceB .scrollB div:eq(0)').css('height', '900px');
// 체결창에 칼럼들 사이즈 조절
$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB .ty01 td').css('width', '25％');
// 체결량을 보여주는 스크립트
var upSum = 0;
var downSum = 0;
var preDiv = document.getElementById('displaydiv');
if (preDiv != undefined) preDiv.remove();
if (intervalId != undefined) clearInterval(intervalId);
var updiv = document.createElement('div');
updiv.id = 'displaydiv';
updiv.style.width = '700px';
updiv.style.position = 'fixed';
updiv.style.top = '50px';
updiv.style.left = '0px';
updiv.style.zIndex = '999';
var upele = document.createElement('input');
upele.style.width = '100px';
upele.style.height = '30px';
upele.style.textAlign = 'right';
upele.id = 'upele';
var upbtn = document.createElement('button');
upbtn.textContent = 'Clear';
upbtn.style.width = '100px';
upbtn.style.height = '30px';
upbtn.id = 'upbtn';
upbtn.addEventListener('click', function () ｛
    if (this.id == 'upbtn') ｛
        upSum = 0;
        document.getElementById('upele').value = 0;
    ｝ else ｛
        downSum = 0;
        document.getElementById('downele').value = 0;
    ｝
    this.blur();
｝);
var downele = upele.cloneNode(true);
downele.id = 'downele';
var downbtn = upbtn.cloneNode(true);
downbtn.id = 'downbtn';
downbtn.addEventListener('click', function () ｛
    if (this.id == 'upbtn') ｛
        upSum = 0;
        document.getElementById('upele').value = 0;
    ｝ else ｛
        downSum = 0;
        document.getElementById('downele').value = 0;
    ｝
    this.blur();
｝);
var rateele = upele.cloneNode(true);
rateele.id = 'rateele';
updiv.appendChild(upele);
updiv.appendChild(upbtn);
updiv.appendChild(downele);
updiv.appendChild(downbtn);
updiv.appendChild(rateele);
document.body.appendChild(updiv);
var lastElement = '';
var intervalId = setInterval(function () ｛
    console.log('============start==============');
    let exist = false;
    let firstText = $('.mainB .halfB .rightB table tr:eq(1)').text();
    let upvol = 0;
    let downvol = 0;
    $('.mainB .halfB .rightB table tr').each(function (idx) ｛
        if (idx == 0) return;
        if (exist) return;
        let text = $(this).text();
        if (lastElement == '') ｛
            lastElement = text;
            exist = true;
            return;
        ｝
        if (lastElement == text) ｛
            exist = true;
            return;
        ｝
        let vol = parseFloat($(this).find('td:eq(2)').text().replace(/,/g, ''));
        if ($(this).attr('class') == 'up') ｛
            upvol += vol;
        ｝ else ｛
            downvol += vol;
        ｝
        console.log($(this).attr('class') + ', volume:' + $(this).find('td:eq(2)').text());
    ｝);
    lastElement = firstText;
    upSum += upvol;
    downSum += downvol;
    document.getElementById('upele').value = parseFloat(upSum).toFixed(5);
    document.getElementById('downele').value = parseFloat(downSum).toFixed(5);
    document.getElementById('rateele').value = upSum > 0 && downSum > 0 ? parseFloat(upSum / downSum).toFixed(3) : 0;
｝, 1000);

```

___

## 사용법 2. 즐겨찾기로 등록해서 바로 적용
예전에 @asbear 님이 쓰셨던 방법이 갑자기 떠올라서 적용해 봤습니다.
즐겨찾기에서 스크립트를 작동하게 할 수 있더라고요..
그래서 해봤습니다.

크롬기준입니다..!!

- 크롬 우측 상단에 **점세개 메뉴 - 북마크 - 북마크 관리자** 로 들어갑니다.
![image.png](https://gateway.ipfs.io/ipfs/QmWgT2eYbzanTzpsuugF25ukD9ox6VQHCnQ2kG7vKGN9By)
- 화면 바깥쪽 아무 맨땅에서 **마우스 우클릭 - 새 북마크 추가** 를 해줍니다.
![image.png](https://gateway.ipfs.io/ipfs/QmWgC5PcNT2uqwGh7TA6K2YrKpC5ciio2s8AzGRS57RYPw)
- 북마크 이름에는 본인이 원하시는 값을 쓰시고 아래쪽 URL 에는 아래 스크립트를 입력합니다. 그리고 저장을 누릅니다.

```
 javascript:function upbit()｛$('.mainB .ty01 .halfB .rightB').wrap('<article></article>'); $('.mainB .ty01 .tabB').wrap('<div class="rightB"></div>');$('.mainB .ty01 .rightB:eq(3)').insertAfter('.mainB .ty01 .halfB .leftB');$('.mainB .ty01 .halfB .rightB:eq(1)').css('background-color','#fff');$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB').css('height', '900px');$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB div').css('height', '900px');$('.askpriceB .scrollB').css('height', '900px');$('.askpriceB .scrollB div:eq(0)').css('height', '900px');$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB .ty01 td').css('width', '25％');var upSum = 0;var downSum = 0;var preDiv = document.getElementById('displaydiv');if(preDiv != undefined) preDiv.remove();if(intervalId != undefined) clearInterval(intervalId);var updiv = document.createElement('div');updiv.id = 'displaydiv';updiv.style.width = '700px';updiv.style.position = 'fixed';updiv.style.top = '50px';updiv.style.left = '0px';updiv.style.zIndex = '999';var upele = document.createElement('input');upele.style.width = '100px';upele.style.height = '30px';upele.style.textAlign = 'right';upele.id = 'upele';var upbtn = document.createElement('button');upbtn.textContent = 'Clear';upbtn.style.width = '100px';upbtn.style.height = '30px';upbtn.id = 'upbtn';upbtn.addEventListener('click', function()｛if(this.id == 'upbtn')｛upSum = 0;document.getElementById('upele').value = 0;｝else｛downSum = 0;document.getElementById('downele').value = 0;｝this.blur();｝);var downele = upele.cloneNode(true);downele.id = 'downele';var downbtn = upbtn.cloneNode(true);downbtn.id = 'downbtn';downbtn.addEventListener('click', function()｛if(this.id == 'upbtn')｛upSum = 0;document.getElementById('upele').value = 0;｝else｛downSum = 0;document.getElementById('downele').value = 0;｝this.blur();｝);var rateele = upele.cloneNode(true);rateele.id = 'rateele';updiv.appendChild(upele);updiv.appendChild(upbtn);updiv.appendChild(downele);updiv.appendChild(downbtn);updiv.appendChild(rateele);document.body.appendChild(updiv);var lastElement = '';var intervalId = setInterval(function()｛console.log('============start==============');let exist = false;let firstText = $('.mainB .halfB .rightB table tr:eq(1)').text();let upvol = 0;let downvol = 0;$('.mainB .halfB .rightB table tr').each(function(idx)｛if(idx == 0) return;if(exist) return;let text = $(this).text();if(lastElement == '')｛lastElement = text;exist = true;return;｝if(lastElement == text)｛exist = true;return;｝ let vol = parseFloat($(this).find('td:eq(2)').text().replace(/,/g, ''));if($(this).attr('class') == 'up')｛upvol += vol;｝else｛downvol += vol;｝console.log($(this).attr('class') + ', volume:' + $(this).find('td:eq(2)').text());｝);lastElement = firstText;upSum += upvol;downSum += downvol;document.getElementById('upele').value = parseFloat(upSum).toFixed(5);document.getElementById('downele').value = parseFloat(downSum).toFixed(5);document.getElementById('rateele').value = upSum > 0 && downSum > 0 ? parseFloat(upSum/downSum).toFixed(3) : 0;｝, 1000);｝;upbit();
```

![image.png](https://gateway.ipfs.io/ipfs/QmZz4jTqPpAej7brdPBoXPJYpLTpyqDsUuhF1yhJVNKpAg)

- 거래창으로 가셔서 아까 등록한 즐겨찾기를 클릭하면 적용됩니다.
- 참고로 1탄에서 만들었던 체결화면 위치만 변경하는 스크립트도 즐겨찾기로 하고 싶으신 분들은 아래 스크립트로 즐겨찾기를 등록하시면 됩니다.

```
javascript:function upbitlayout()｛$('.mainB .ty01 .halfB .rightB').wrap('<article></article>');$('.mainB .ty01 .tabB').wrap('<div class="rightB"></div>');var $bottom = $('.mainB .ty01 .rightB:eq(3)');$bottom.insertAfter('.mainB .ty01 .halfB .leftB');$('.mainB .ty01 .halfB .rightB:eq(1)').css('background-color','#fff');$('.askpriceB .scrollB').css('height', '900px');$('.askpriceB .scrollB div:eq(0)').css('height', '900px');$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB').css('height', '900px');$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB div').css('height', '900px');$('.mainB .ty01 .halfB .rightB:eq(1) .scrollB .ty01 td').css('width', '25％');｝;upbitlayout();
```
___

## 기타사항
- Clear 버튼은 각각 매수/매도량을 다시 0으로 설정합니다.(비율도 재조정 됩니다.)
- 종목을 변경하시면 F5로 재조회 이후에 다시 즐겨찾기를 눌러 주셔야 정상 작동합니다.
- 체결량 위치변경 디자인은 적용하지 않고, 그냥 체결량 합계만 보고 싶은 경우 스크립트가 조금 달라집니다. 아래 스크립트를 사용하시면 됩니다.

```
​
var upSum = 0;
var downSum = 0;
var preDiv = document.getElementById('displaydiv');
if(preDiv != undefined) preDiv.remove();
if(intervalId != undefined) clearInterval(intervalId);
var updiv = document.createElement('div');
updiv.id = 'displaydiv';
updiv.style.width = '700px';
updiv.style.position = 'fixed';
updiv.style.top = '50px';
updiv.style.left = '0px';
updiv.style.zIndex = '999';
var upele = document.createElement('input');
upele.style.width = '100px';
upele.style.height = '30px';
upele.style.textAlign = 'right';
upele.id = 'upele';
var upbtn = document.createElement('button');
upbtn.textContent = 'Clear';
upbtn.style.width = '100px';
upbtn.style.height = '30px';
upbtn.id = 'upbtn';
upbtn.addEventListener('click', clearText);
var downele = upele.cloneNode(true); // true means clone all childNodes and all event handlers
downele.id = 'downele';
var downbtn = upbtn.cloneNode(true);
downbtn.id = 'downbtn';
downbtn.addEventListener('click', clearText);
var rateele = upele.cloneNode(true);
rateele.id = 'rateele';
updiv.appendChild(upele);
updiv.appendChild(upbtn);
updiv.appendChild(downele);
updiv.appendChild(downbtn);
updiv.appendChild(rateele);
document.body.appendChild(updiv);
var lastElement = '';
function clearText()｛
if(this.id == 'upbtn')｛
upSum = 0;
document.getElementById('upele').value = 0;
｝else｛
downSum = 0;
document.getElementById('downele').value = 0;
｝
this.blur();
｝
function sumVolume()｛
console.log('============start==============')
let exist = false;
let firstText = $('.mainB .tabB:eq(2) .scrollB table tbody tr:eq(0)').text();
let upvol = 0;
let downvol = 0;
$('.mainB .tabB:eq(2) .scrollB table tbody tr').each(function(idx)｛
if(exist) return;
let text = $(this).text();
if(lastElement == '')｛
lastElement = text;
exist = true;
return;
｝
if(lastElement == text)｛
exist = true;
return;
｝
let vol = parseFloat($(this).find('td:eq(2)').text().replace(/,/g, ''));
if($(this).attr('class') == 'up')｛
upvol += vol;
｝else｛
downvol += vol;
｝
console.log($(this).attr('class') + ', volume:' + $(this).find('td:eq(2)').text());
// console.log(lastElement + ":" + text);
｝);
lastElement = firstText;
upSum += upvol;
downSum += downvol;
document.getElementById('upele').value = parseFloat(upSum).toFixed(5);
document.getElementById('downele').value = parseFloat(downSum).toFixed(5);
document.getElementById('rateele').value = upSum > 0 && downSum > 0 ? parseFloat(upSum/downSum).toFixed(3) : 0;
｝
var intervalId = setInterval(sumVolume, 1000);
```
- 추가로 궁금하신 사항있으시면 댓글 달아주십시오.(시간이 허락한다면.. ㅎ)

___

역시 프로그래머는 자신이 만든 프로그램을 써주시는 분들이 응원해주실때 힘이 나는 것 같습니다.
1탄에서 만든 정도로도 많은 분들이 감사해 하셔서.. 저도 감사드립니다..!!
그런 상황에서 요청사항을 보니 또 바로 타자를 두들기게 되는군요. 무려 새벽3시 까지... ㅎㅎ
원래 프로그램이란게 기능을 하나만더 하나만더 하다보면 시간이 훌쩍지나가버리거든요.

아무튼 저로서도 재미로 만들어보기에 좋은 기회였던것 같네요.
아무쪼록 도움이 되시는 분들이 많길 바라며..... 모두들 성투하시기 바랍니다..!!
