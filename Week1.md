## 目前任务

1. 寻找需求 3-5个。评估开发难度，尽量每个在1-2周可以完成基本开发
   - 从ifttt等吸取一些经验，它们哪些暂时无法很好的做到。
   - 有没有其他吐槽需求比较多的来源
2. 网站后台接入方式，前期可以纯静态页面，之后还是需要后台的。选择一个适合快速开发的语言，初步考虑是PHP或者Go、Python这些的。
3. 这周画一个简单的架构，主要开发集中在网关部分。



## 日程安排

D1-D2 完成初步架构图

D3 分析一下ifttt的使用方式

D4-D7 开发网关，需要做限速、鉴权、API转发。



## 每日进展

### 7.13 微信群记录打卡信息的需求

需求描述：聊天的时候，临时发现了这个需求。我们有一个打卡群，出于互动的考虑，希望大家在群里打卡。然而，后续收集打卡信息会很麻烦，需要人工一个个信息复制收集。而目前按照微信官方对信息管控的程度，没有什么现有工具可以直接替代人力来做这个事情。

解决思路：

- 最开始是希望使用UiBot、UiPath这些RPA工具来进行自动化操作的。然而实际操作起来，发现很难定义文本框的区域。

- 尝试了使用按键精灵，理论上是可行的，但是操作不够方便，且功能有限，很容易出错。
- 开始查找一些代码解决的思路，分为几种：
  - web api，但是目前基本不可用了。大部分账号已经被禁用web登录
  - 通过模拟器等手段，拿到db数据，解析db。感觉是一个可行的思路，但是比较复杂，而且是很久之前的方案了，不确定现在是否还可行。
  - hook的方式，接收新的请求，然后进行处理。这个是看起来最可行的方案。目前git上也有一些人给出了实现方案



PS： 

1. 好用的RPA平台接口开发，可能会是一个不错的第二职业。
2. RPA基本都没有实现mac版本。
3. 这个需求其实看到一半的时候，有些犹豫了。因为即使我去实现了，可能也会不久后被封禁。并且我个人认为，官方应该也在研究新的解决思路，之后可能会给出API等。这个问题是一个特殊时间段的需求。



### 7.14 - 7.15 进展维艰

最近两天基本没有进展，一个原因是个人时间问题，另一个原因是：

大部分需求其实可以用不写代码的方式解决的。

我觉得解决问题是第一目的，不能拿着锤子找钉子。

所以，目前的局面有些尴尬。

如果真的没有什么合适的需求，往单纯的问题解决方案分享网站发展，也是有可能的。



### 7.16 IFTTT

https://platform.ifttt.com/

IFTTT - if this then that，主要是一个任务流的概念。当服务A触发xxx后，服务B进行yyy

大致原理如下（并不保证准确，只是看了大概原理）：

- 所有支持的服务需要在IFTTT平台注册，并进行必要信息的转发。
- 需要进行服务的链接，对参数进行转换，完成A到B的传递。
- 当服务A收到请求后，发起请求到IFTTT。之后IFTTT检测到链接，再转发到服务B



优点：

- 已经有一定规模了，600个服务，互相连接会比较方便。
- 已经有了标准话流程，新服务只要自己进行对接即可。

缺点：

- 对国内用户不算友好，大部分相关账号网站无法登录。
- 感觉相对于收益来说，进行定制的成本稍微有点高。也可能是我没想到好的场景。



### 7.17 - 7.19 外出活动

出门参加了3天活动，精力完全透支。

感觉想每天固定时间开发，确实有点天真了。打算放慢这边的速度，先把其他事情处理完。