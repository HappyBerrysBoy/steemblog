---
title: 'Steem Tool(1.1.12) : Add Tag Shortcut Function and Animation Effect'
tags:
  - utopian-io
  - development
  - busy
  - kr-dev
  - steemtool
author: happyberrysboy
categories: dev
excerpt: "<img src=\"https://github.com/steemhappyberrysboy/steem_design_tool\" />\r\n#### Repository   <br>  <br>  ### New Features - **What feature(s) did you add?**  <br> <center><h3>1. Tag Shortcuts</h3>/cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_0....."
date: 2018-07-20 01:38:24
---

#### Repository
https://github.com/steemhappyberrysboy/steem_design_tool

<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)
<br>

### New Features
- **What feature(s) did you add?**

<br>
<center><h3>1. Tag Shortcuts</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- Add tag shortcut function.
- Input the tag you want to register as a shortcut in **Input Tag**
- The Tag is added to the lower container
- Click the tag button to go to the tag page

![](https://steemitimages.com/0x0/https://cdn.steemitimages.com/DQmdD4qNSfVfFEZJD1qzkaDjp24SDTpE6NbwAmdtp6TkkR9/tagshortcutkr.gif)


<br>
<center><h3>2.  Animation</h3>https://steemitimages.com/80x0/https://cdn.steemitimages.com/DQmeBM8uYHoA6vNfhKWffgTb2GsuB4iBZwWWV4hESwi4gTg/border_05.png
</center>

- Added some animation to give a little more liveliness and fun.
- Used open source [Animate.css](https://daneden.github.io/animate.css/)

![animation.gif](https://ipfs.busy.org/ipfs/Qmb4Ec6SeY5U28XoLrrRWyXndXKfE8GQiMD3wH1ndP7hts)





- **How did you implement it/them?**

- Add Animate.css
- Add Semantic.js
- Expend jquery function for animateCss

```
// ===== popup.html =====
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.5.2/animate.min.css"> 
<script src="thirdParty/semantic.min.js"></script>

// ===== common.js =====
// Apply Semantic-ui accordion design 
$('.ui.accordion').accordion();

// Animate.css extend in Jquery 
$.fn.extend(｛
  animateCss: function(animationName, callback) ｛
    var animationEnd = (function(el) ｛
      var animations = ｛
        animation: 'animationend',
        OAnimation: 'oAnimationEnd',
        MozAnimation: 'mozAnimationEnd',
        WebkitAnimation: 'webkitAnimationEnd',
      ｝;

      for (var t in animations) ｛
        if (el.style[t] !== undefined) ｛
          return animations[t];
        ｝
      ｝
    ｝)(document.createElement('div'));

    this.addClass('animated ' + animationName).one(animationEnd, function() ｛
      $(this).removeClass('animated ' + animationName);

      if (typeof callback === 'function') callback();
    ｝);

    return this;
  ｝,
｝);

// ===== srcManager.js =====
// Apply Animation
  $('#copied').animateCss('flip', (() => (setTimeout(copied.style.display = 'none'), 3000)));
```

<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)
<br>

### Roadmap
- Add new features using steemjs
- Make image/html source group tab

<br>
![](https://ipfs.busy.org/ipfs/QmUKxtLW5JEnqaaAnwiLc9kFK1BqpcMGoFKTF7JLKcvJqy)


#### GitHub Account
https://github.com/steemhappyberrysboy
