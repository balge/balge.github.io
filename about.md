---
bg: owl.jpg
layout: page
title: About
crawlertitle: Crab Resume
permalink: /about/
active: about
---

## 先讲讲怎样才是一份好的技术简历

 - Feature：是什么
 - Advantage：比别人好在哪些地方
 - Benefit：如果雇佣你，招聘方会得到什么好处 

其次，写简历和写议论文不同，过分的论证会显得自夸，反而容易引起反感，所以要点到为止。这里的技巧是，提供论据，把论点留给阅读简历的人自己去得出。放论据要具体，最基本的是要数字化，好的论据要让人印象深刻。

举个例子，下边内容是虚构的：

2006年，我参与了手机XX网发布系统WAPCMS的开发（```这部分是大家都会写的```）。作为核心程序员，我不但完成了网站界面、调度队列的开发工作，更提出了高效的组件级缓存系统，通过碎片化缓冲有效的提升了系统的渲染效率。（```这部分是很多同学忘掉的，要写出你在这个项目中具体负责的部分，以及你贡献出来的价值。```）在该系统上线后，Web前端性能从10QPS提升到200QPS，服务器由10台减少到3台（``` 通过量化的数字来增强可信度 ```）。2008年我升任WAPCMS项目负责人，带领一个3人小组支持着每天超过2亿的PV（``` 这就是Benefit。你能带给前雇主的价值，也就是你能带给新雇主的价值。 ```）。

有同学问，如果我在项目里边没有那么显赫的成绩可以说怎么办？讲不出成绩时，就讲你的成长。因为学习能力也是每家公司都看中的东西。你可以写你在这个项目里边遇到了一个什么样的问题，别人怎么解决的，你怎么解决的，你的方案好在什么地方，最终这个方案的效果如何。

具体、量化、有说服力，是技术简历特别需要注重的地方。

（以上内容在写完简历后，对每一段进行评估，完成后再删除）

---


# 联系方式

- 手机：18767156042
- Email：18767156042@163.com
- QQ/微信号：2361105260/18767156042

---

# 个人信息

 - 吴城霸（螃蟹）/男/1992 
 - 本科/理工大学机电系 
 - 工作年限：3年以上
 - 个人博客：[http://balge.github.io](http://balge.github.io)
 - 期望职位：Web前端高级程序员
 - 期望薪资：税前月薪16k~20k
 - 期望城市：杭州

---

# 工作经历

### 杭州智才广赢信息技术有限公司 （ 2015年3月 ~ 至今 ）
 - 前端主要是阿里云业务的外包


#### 大众点评webapp --- react，webpack学习 

项目背景：为了深入学习react,router,redux等

构建工具：create-react-app; [webpack构建在其他demo中](https://github.com/balge/webpack-demo)

工作任务: 主页面和全部子页面

困难问题：
  - 脚手架不支持less
  - nodejs本地服务koa，模拟数据请求
  - koa服务再3005端口，项目调试地址3000端口，涉及到跨域
  - redux的状态管理理解，流程
  - 木偶组件和智能组件的划分

处理方式：
  - 翻阅了[文档](https://segmentfault.com/a/1190000010162614),根据文档增加less配置
  - 翻阅了[文档](http://www.ituring.com.cn/article/274839)和视频
  - 通过packjson.json设置[proxy实现](https://segmentfault.com/q/1010000008508440/a-1020000008516740/revision)
  - [文档](http://www.redux.org.cn/docs/basics/Actions.html),学习todolist的demo，高级部分还在学习中
  - 通过教学视频，智能组件-获取数据、定义数据操作的相关函数，然后将这些数据、函数直接传递给具体实现的组件；木偶组建-从智能组件（或页面）那里接受到数据、函数，然后就开始做一些展示工作


#### 云栖社区项目

项目背景：线上一期页面基础上迭代

构建工具：Dawn（后续将简称为 DN），是阿里云前端团队，新一代的前端构建工具，简化并统一了针对开发人员的「命令行接口」

工作任务：主要负责[首页](https://yq.aliyun.com/)，[博客](https://yq.aliyun.com/articles)，[下载](https://yq.aliyun.com/download)，[专家](https://yq.aliyun.com/expert)的前端展示＋数据联调＋常用组件封装，例如[mark,follow](https://yq.aliyun.com/download/2470)等。

困难问题：
  - 熟悉代码--在一期基础上，快速熟悉文件结构和代码，避免组件冲突，样式冲突;
  - 首页活动消息日历部分 ![json返回](https://img.alicdn.com/tfs/TB12F7KeTtYBeNjy1XdXXXXyVXa-1057-303.png "json返回")

  1)开始对业务交互有误解（每次点击请求当天数据），导致json结构需要重新定义

  2)当天存在活动，日历返回当天，页面没问题

  3)当天不存在活动，默认返回距离nowDate最近的后面一个date，页面报错异常

  4)对存在活动的日期做特殊标记，并且有点击交互事件锚点到对应日期活动

  5)项目前后端协同开发，导致上传gitlab代码冲突


处理方式：
  - 重新和交互确定细节（渲染全部数据，点击日期锚点），和后端定义结构
  - 查看代码，不理解的地方和第一期前端即使沟通，对js插件文件进行分类，加强复用性
  - 完善mock的json返回，对3）的情况进行js的修改
  - 开始准备改造日历插件，改完之后出现插件有复用导致影响了页面其他功能，最后放弃这个方法，在日历初始化完成后，和actlist的json列表对比，给匹配的日期加上特定事件和样式
  - 查阅了git命令的[文档]()

项目成长：
  - 能熟练阅读他人代码并在此基础上改造
  - 做项目之前，做好时间把控，有效率得投入
  - 对git命令又了更深入理解，能独立解决代码冲突和分支管理


#### 2017年阿里云双11，2018年3月阿里云采购季 

项目背景：阿里云产品促销，通过领取红包达到引导消费目的

工作任务：红包分享活动pc+h5，页面已下线[双11](https://promotion.aliyun.com/ntms/m/act/end20171111.html),[采购季](https://promotion.aliyun.com/ntms/act/season.html)，图示如下：

![设计稿](https://img.alicdn.com/tfs/TB1myuYpSBYBeNjy0FeXXbnmFXa-779-632.png "设计稿")

主要功能： 1.顶部大红包领取一次；2.分享按钮立即成为云大使，并显示分享界面，并且抽奖次数+1，好友通过分享链接进入页面领取顶部大红包，视为邀请成功；3.邀请达标，领取额外红包；4.转盘抽奖，分享一次增加一次机会，一天最多一次机会，机会可累加。

项目成长：前后端同时开发，根据前端逻辑定义接口字段，打通接口和接口之间的关联；对深度bug定位，提高了应用的传播率。


#### 2017天猫双11成交额竞猜

项目背景：竞猜双11天猫成交额

工作任务：还原h5，后端联调提交竞猜额，用户只能提交一次竞猜额，[线上地址](https://m.aliyun.com/act/guess1111)

困难问题：竞猜额选择器和选择器优化

处理方式：参考了github中的[mobileSelect](https://github.com/onlyhom/mobileSelect.js/blob/master/docs/README-CN.md)形成初步转盘；
通过以下代码改造selectjs源码，判断选择器到底部和到顶部，模拟跑马灯

```
if (_this.curDistance[index] + _this.offsetSum > 2 * _this.liHeight) {
  // alert('到顶！')
  _this.curDistance[index] = _this.oversizeBorder + 11 * _this.liHeight;
  $(theSlider).eq(index).find('li').eq(10).addClass('active').siblings('li').removeClass('active');
  $(theSlider).removeClass('addAnim');
  setTimeout(function() {
    _this.movePosition(theSlider, _this.curDistance[index]);
  }, 100);

} else if (_this.curDistance[index] + _this.offsetSum < _this.oversizeBorder) {
  _this.curDistance[index] = -9 * _this.liHeight;
  $(theSlider).eq(index).find('li').eq(11).addClass('active').siblings('li').removeClass('active');
  $(theSlider).removeClass('addAnim');
  setTimeout(function() {
    _this.movePosition(theSlider, _this.curDistance[index]);
  }, 100);
}
```

项目成长：能阅读插件源码，并对它做一些功能上的修改


#### 云栖大会购票系统

项目背景：为云栖大会开发一套购票系统，[项目地址](https://portal.aliyun.com/page/ticket),已经过期重定向到首页。

工作任务：主要负责票务选择页面，我的票务界面，主要是学习目的，和阿里同学一起参与开发。

项目成长：对vue有了基础认识，还需要系统学习一下。



---

## 学习作品
  - [熟悉webpack](https://github.com/balge/webpack-demo)
  - [webapp-大众点评](https://github.com/balge/webapp-dianping)

## 技能清单

以下均为我熟练使用的技能

- 前端框架：Bootstrap/Jquery/React/React-router/Redux
- 版本管理、文档和自动化部署工具：Git


---

# 致谢
感谢您花时间阅读我的简历，期待能有机会和您共事。
