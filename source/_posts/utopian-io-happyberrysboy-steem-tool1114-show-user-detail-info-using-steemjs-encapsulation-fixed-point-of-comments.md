---
title: >-
  Steem Tool(1.1.14) : Show User Detail info using steemjs / Encapsulation /
  Fixed point of comments
tags:
  - utopian-io
  - development
  - kr-dev
  - steemtool
  - kr
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://cdn.steemitimages.com/DQmQkwXoqfSgSjVPrXNEthFr5dNzWmjjVHf3XLGokRfHDn2/KakaoTalk_20180723_160127841.png\" />\r\n![KakaoTalk_20180723_160127841.png](  #### Repository   <br>  <br>  ### New Features - **What feature(s) did you add?**  [Previous posting : Steem Tool(1.1.12) : Add Tag Shortcut Function and Animatio....."
date: 2018-07-24 03:22:51
---

![KakaoTalk_20180723_160127841.png](https://cdn.steemitimages.com/DQmQkwXoqfSgSjVPrXNEthFr5dNzWmjjVHf3XLGokRfHDn2/KakaoTalk_20180723_160127841.png)

#### Repository
https://github.com/steemhappyberrysboy/steem_design_tool

<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)
<br>

### New Features
- **What feature(s) did you add?**

[Previous posting : Steem Tool(1.1.12) : Add Tag Shortcut Function and Animation Effect](https://steemit.com/utopian-io/@happyberrysboy/steem-tool-1-1-12-add-tag-shortcut-function-and-animation-effect)

I added two new features to my previous posting but I was not selected.  :(
So I added more features here.

First, the features introduced in the previous post.

<br>
<center><h3>1. Tag Shortcuts</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- [github address](https://github.com/steemhappyberrysboy/steem_design_tool/commit/978877696d8c8af1301464bf91fda9e3c468bda3#diff-82eb748a552f82499c2b7b3dd4b5d727R27)
- Add tag shortcut function.
- Input the tag you want to register as a shortcut in **Input Tag**
- The Tag is added to the lower container
- Click the tag button to go to the tag page

![](https://steemitimages.com/0x0/https://cdn.steemitimages.com/DQmdD4qNSfVfFEZJD1qzkaDjp24SDTpE6NbwAmdtp6TkkR9/tagshortcutkr.gif)


<br>
<center><h3>2.  Animation</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- [github address](https://github.com/steemhappyberrysboy/steem_design_tool/commit/5431cdf67d94f363d6e25a7ef851c0b11a89fcbf)
- Added some animation to give a little more liveliness and fun.
- Used open source [Animate.css](https://daneden.github.io/animate.css/)

![animation.gif](https://ipfs.busy.org/ipfs/Qmb4Ec6SeY5U28XoLrrRWyXndXKfE8GQiMD3wH1ndP7hts)


<br>
### New features this posting


<center><h3>3. User Sorting</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- [github address](https://github.com/steemhappyberrysboy/steem_design_tool/commit/ae6ef9ce19f0f4ed9ef0b5fef3fae00acb09ac00)
- User orders can be sorted in ABC order.

![](https://steemitimages.com/0x0/https://ipfs.busy.org/ipfs/QmXs96SR9Z6n5khFEdLsexHX86cQUjAi88YysevF4GCVJ9)


<br>
<center><h3>4. User Detail</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- [github address](https://github.com/steemhappyberrysboy/steem_design_tool/commit/39ec7f260f87285b8b2611b5686914f0f637dccf)
- **Steemjs** attached.
- You can see the details of the user.
- I will add more user information here in the future.

![](https://steemitimages.com/0x0/https://ipfs.busy.org/ipfs/QmeeUYVLECuFiF7p6mBdrHDX2nNps53csv5KgeKqHLEEXQ)


<br>
<center><h3>5. Fixed point of @gregory.latinier 's comments</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- Use **CONST** instead of **LET** where do not need it. [github address](https://github.com/steemhappyberrysboy/steem_design_tool/commit/ca5e81fa1e7a8e92adefe98c894dfedca8932210)
- Use **i+=1** instead of **++**
- Remove unnecessary annotations


<br>
<center><h3>6. Encapsulation</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- [github address](https://github.com/steemhappyberrysboy/steem_design_tool/commit/1bb89cf8b6faf68db2b3e78f3353e7181a3c2c18)
- Refactoring and encapsulation most of the js files like below sample.  

```
!function(parameters)｛
...
...
｝(parameters);
```

<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)


- **How did you implement it/them?**

- Add Animate.css
- Add Semantic.js
- Add Steemjs for api 
- Expend jquery function for animateCss



<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)


#### GitHub Account
https://github.com/steemhappyberrysboy
