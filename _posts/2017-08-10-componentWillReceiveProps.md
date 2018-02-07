---
bg: tools.jpg
layout: post
title: react之componentWillReceiveProps
crawlertitle: react生命周期
summary: react生命周期
date: '2017-08-10 10:30:00 +0700'
categories: posts
tags:
  - react
author: Crab
---

需求场景：一行3列布局，每次请求接口，返回10条数据，每一个数据加入到最短一列，到底请求pagesize+1;筛选城市，渲染新数据

# react之componentWillReceiveProps
先上需求效果：![需求效果](https://img.alicdn.com/tfs/TB1V.BIX_tYBeNjy1XdXXXXyVXa-1205-713.png "需求效果")
[参考文档1](https://www.jianshu.com/p/4784216b8194)
[参考文档2](https://segmentfault.com/q/1010000007890694/a-1020000007890972)
### 设计思路
* 1.父组件请求返回10组数据，对其遍历不断改变state的值，切换筛选条件，清空state

```
for (let i = 0; i < data.length; i++) {
    this.setState({
        listContent: this.state.listContent.concat(data.slice(0, i + 1))
    });
}
```
* 2.子组件的componentWillReceiveProps函数接收改变后的props

```
this.state = {
    c1: [], //1列
    c2: [], //2列
    c3: [] //3列
};
componentWillReceiveProps(nextProps) {
    const minCol = this.getShortestColumn().minCol;
    if (minCol === 0) {
        this.setState({
            c1: this.state.c1.concat(nextProps.val.slice(nextProps.val.length - 1, nextProps.val.length))//每次把nextprops的最后一个元素concat到原来已有state
        });
    }
    if (minCol === 1) {
        this.setState({
            c2: this.state.c2.concat(nextProps.val.slice(nextProps.val.length - 1, nextProps.val.length))
        });
    }
    if (minCol === 2) {
        this.setState({
            c3: this.state.c3.concat(nextProps.val.slice(nextProps.val.length - 1, nextProps.val.length))
        });
    }
}
getShortestColumn() { //获取最短列
    const h1 = document.getElementById('col1').offsetHeight;
    const h2 = document.getElementById('col2').offsetHeight;
    const h3 = document.getElementById('col3').offsetHeight;
    const total = document.getElementById('totalCol').offsetTop;
    let minH = h1,
        minCol = 0;
    if (h2 < minH) {
        minH = h2;
        minCol = 1;
    }
    if (h3 < minH) {
        minH = h3;
        minCol = 2;
    }
    return { minH: minH, minCol: minCol, total: total };
}
```
* 3.加入投票，分享弹窗等功能
