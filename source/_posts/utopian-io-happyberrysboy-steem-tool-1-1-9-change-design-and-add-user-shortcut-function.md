---
title: 'Steem Tool(1.1.9) : Change Design and Add User Shortcut Function'
tags:
  - utopian-io
  - development
  - busy
  - kr
  - kr-dev
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://github.com/steemhappyberrysboy/steem_design_tool\" />\r\n#### Repository   <br>  <br>  ### New Features - **What feature(s) did you add?**  <br> <center><h3>1. Design</h3>/cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png <....."
date: 2018-07-13 22:29:39
---

#### Repository
https://github.com/steemhappyberrysboy/steem_design_tool

<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)
<br>

### New Features
- **What feature(s) did you add?**

<br>
<center><h3>1. Design</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- Add open source UI component [**Semantic-ui**](https://semantic-ui.com/)
- Semantic-UI is very simple and easy to use.
```
// Sample Design
// Simple Button 
<div class="ui button">Follow</div>
```

![image.png](https://ipfs.busy.org/ipfs/QmQRw91C6ewVBDQ76skGBZN8owwBWW7Rp7ANAVzhEuqiSY)


```
//Icon Button
<div class="ui labeled button" tabindex="0">
  <div class="ui button">
    <i class="heart icon"></i> Like
  </div>
  <a class="ui basic label">
    2,048
  </a>
</div>

```
![image.png](https://ipfs.busy.org/ipfs/QmZPUQ6da9FcUGYAdaaTgsDP1joUAvrersMGS7xg7ngNZD)

- The design has been changed as follows.

### Before 
![image.png](https://ipfs.busy.org/ipfs/QmU75NUgs1rsiyWaf7R48KuCb985Fub5Ae8kDvdUwMb3RW)

### After
![image.png](https://ipfs.busy.org/ipfs/QmU6C82dRSyT2VsFnHuESvj1QooUDT7HQycbCCYpsSg2gE)

- I made it an accordion type to add more features  in the future.

![steemtool4.gif](https://ipfs.busy.org/ipfs/QmdyYz9zCkzKSLmdapiMy2RJaae51bfVSBmEYgbCeBohkN)
<br>
![steemtool3.gif](https://ipfs.busy.org/ipfs/QmPBubtcQ7Xd9UVSFW2MLjaQq6XiUXd2WaSjiPvr5R4rtt)


<br>
<center><h3>2. User Shortcuts</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- Add user shortcut function.
- Enter the user ID you want to register as a shortcut in **Input @ID**
- The ID is added to the lower container
- Click the ID button to go to the user's page

![steemtool5.gif](https://ipfs.busy.org/ipfs/QmaFh5b7UXmDhpFbXG3n9HemLqCKZg9Vj1GgHjNukUJtd3)





- **How did you implement it/them?**
Most sources have changed.
The file is divided into several sections according to functions and the file name is also modified accordingly.

![image.png](https://ipfs.busy.org/ipfs/QmP8MTfbyvhxL38amMjTRbsoespJHwXakknLQUz157V3o7)


<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)
<br>

#### GitHub Account
https://github.com/steemhappyberrysboy
