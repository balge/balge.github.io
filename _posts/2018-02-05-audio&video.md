---
bg: tools.jpg
layout: post
title: Video、Audio碰上的坑
crawlertitle: 开发中碰上的坑
summary: 有哪些跳过的坑
date: '2018-02-05 10:30:00 +0700'
categories: posts
tags:
  - H5 JS
author: Crab
---

H5传播页面在微信端，钉钉端，浏览器端越来广泛。

# `Video Audio`元素
通常，页面有大篇幅全屏动画引导，都需要用到video来低成本得实现效果

#### 1坑：ios会默认弹出视频窗口播放，出现controls，遮挡页面其它交互
* webkit-playsinline="true" 让视频在IOS浏览器小窗内播放，也就是不是全屏播放
* playsinline="true" IOS微信浏览器支持小窗内播放
* x5-video-player-fullscreen="true" 全屏播放

#### 2坑：wx端通常不自动播放
* 微信的WeixinJSBridgeReady事件
[参考文档](http://qydev.weixin.qq.com/wiki/index.php?title=WeixinJS%E6%8E%A5%E5%8F%A3&oldid=287)
```
function forceSafariPlayAudio() {
    document.removeEventListener('WeixinJSBridgeReady', forceSafariPlayAudio, false);
    video.load(); // iOS 9   还需要额外的 load 一下, 否则直接 play 无效
    video.play(); // iOS 7/8 仅需要 play 一下
}
document.addEventListener('WeixinJSBridgeReady', forceSafariPlayAudio, false);
```

#### 3坑：安卓（测试问题机型：华为手机，oppo手机，例如长按播放声音），声音无法暂停
* 参考文档并不能解决我的问题，只是提供了一种思路[参考文档](http://www.mizuiren.com/398.html)
* 第一次处理方式,再安卓uc下，touchstart之后，声音开始播放，touchend之后，声音不暂停
```
dom.find('.start-btn').on('touchstart', function(event) {
    event.preventDefault();
    var audio = document.getElementById('audio' + index);
    audio.volume = 1.0;
    audio.play();
    console.log(audio.paused);//一直为true
}).on('touchend', function(event) {
    event.preventDefault();
    var audio = document.getElementById('audio' + index);
    audio.pause();
    audio.currentTime = 0;
});
```
* 监听play，再播放完成后停止并移除video，解决问题
```
video.addEventListener('play', function() {
    video.onended = function() {
      video.pause();
      video.remove();
    };
}, false);
```

