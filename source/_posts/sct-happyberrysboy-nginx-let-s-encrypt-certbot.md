---
title: 간단하게 알아보는 Nginx에 Let’s Encrypt 인증서 발급 및 Certbot 설치
tags:
  - sct
  - sct-kr
  - sct-freeboard
  - sct-dev
  - jjm
  - zzan
  - liv
  - palnet
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://cdn.steemitimages.com/DQmeVyCnkva2SjkjT5mk9XPo2BJzbK7szFE1pDqqAHrSBsC/WHALE_TITLE_COLORED_LOW.jpg\" />\r\n![WHALE_TITLE_COLORED_LOW.jpg](  안녕하세요, 햅뽀이입니다.  처음으로 이 대문을 써보는것 같아요. 예전에 스팀이 아주 많이 활성화 되어 있을 때, 능력자 @thecminus 님이 판매하던 이미지들 이었는데요.     여기 있군요. 그리고 그외에 더 많은 아주 이쁜 그림들 입니다.  저는 이 고래와 소녀에서 소녀의 미소가 너무너무너....."
date: 2019-09-06 17:33:33
---

![WHALE_TITLE_COLORED_LOW.jpg](https://cdn.steemitimages.com/DQmeVyCnkva2SjkjT5mk9XPo2BJzbK7szFE1pDqqAHrSBsC/WHALE_TITLE_COLORED_LOW.jpg)

안녕하세요, 햅뽀이입니다.

처음으로 이 대문을 써보는것 같아요. 예전에 스팀이 아주 많이 활성화 되어 있을 때, 능력자 @thecminus 님이 판매하던 이미지들 이었는데요. 

![](https://cdn.steemitimages.com/DQmVVfaSJV1orCwB63cxXEJr7YPwCFxU7hWiwfJrhU7zQK1/image.png)

여기 있군요. 그리고 그외에 더 많은 아주 이쁜 그림들 입니다.

저는 이 고래와 소녀에서 소녀의 미소가 너무너무너무너무너무너무 마음에 들어 구입하게 되었고 지금까지 프사로 사용하고 있었네요.. ㅎㅎ

https://tool.steem.world/Shop?type=1 여기에서 판매하고 있습니다!! ㅎㅎ

이 이야기는 여기까지!!

___

지금 급히 https를 설정해야 할 곳이 있어서!!  이해는 거기까지.. 명령어만으로 설치하는 법을 포스팅 해봅니다. 

> OS : ubuntu 18.04
Web Server : nginx


___

###  Nginx 설치
```
sudo apt-get install nginx
```

###  Let's Encrypt 사이트의 Certbot 설치
- 여기로 접속합니다.!! https://certbot.eff.org/

![](https://cdn.steemitimages.com/DQmRj8vZz6HS6HTy2cybYjQUWvaRF1v8hcuJ9WqsdF2TeHy/image.png)
- 아래와 같이 나오는데 여기서 웹서버 및 운영체제 선택 해줍니다.
- 선택과 동시에 사이트가 바로 이동하게 됩니다.
- 알려주는 사이트에서 시키는 대로 진행!!

![](https://cdn.steemitimages.com/DQmRksaw4e75aT42dnxvkFuHjfEKkEp7Gx6mGrPma4fBWNJ/image.png)

```
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update

sudo apt-get install certbot python-certbot-nginx

sudo certbot --nginx
```

###  https는 443 Port를 사용함으로 열어주셔야하고요!!

###  nginx 설정
```
cd /etc/nginx/sites-available
sudo vi default
```

![](https://cdn.steemitimages.com/DQmT5Wa2sLAmVU8f4bJydeT7fgXxaAwiKnVKRm7W82eE8RR/image.png)

- 중간즈음 location / 부분이 https로 접속하면 연결되는 부분입니다.
- 저의 경우 8080에서 node로 돌아가는 서비스와 연동을 하였기 때문에 아래와 같이 작성하였습니다.

```
location / ｛
                proxy_pass http://127.0.0.1:8080;
                proxy_http_version 1.1;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'upgrade';
                proxy_set_header Host $host;
                proxy_cache_bypass $http_upgrade;
                # First attempt to serve request as file, then
                # as directory, then fall back to displaying a 404.
                try_files $uri $uri/ =404;
        ｝

```
- 각자 서버에서 돌아가는 서버의 Port를 설정하여 주시면 됩니다.