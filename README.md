# pdown
---
百度网盘下载器，2020,百度网盘高速下载
> PDown是个人项目，开始是为了方便宿舍下载试验资料。 现在分享出来希望可以帮助到更多的人

![demo](down600.gif)


#### [蓝奏云 下载地址  https://www.lanzous.com/iaf304h](https://www.lanzous.com/iaf304h)
---
### 0.项目刚发布，确实有不少BUG，请参阅 [更新日志.md](更新日志.md)  
最新更新时间：2020-3-21 13:00，近期我们更新很频繁的，如果遇到某个链接不能下载，过一天再试BUG可能就被修复了，请留意我们的版本更新。过一个月程序就稳定了，就不会有频繁的版本更新了<br/><br/>

> 在3月25日之前，会频繁的停服更新，所以大家加会遇到各种不能下载，无限拉取。请多包容。我一直在改进，很快就会稳定了。不要因此放弃我啊<br/>

### 1.安装使用

软件是单文件.exe(5MB) 无需安装,下载后双击直接运行<br/>
直接粘贴  **完整的**  百度分享链接和**提取码**，就可以下载了。不需要登录你的百度账号<br/>
总有人只粘贴分享链接不包括提取码, 应该像这样粘贴完整的链接+提取码<br/>

```
链接：https://pan.baidu.com/s/1jxP5vznx3_XvHrPKv1yhKg 提取码：97zc 
```

### 2.加速原理

你提交链接  -->  我使用VIP账号去下载到我的服务器  -->  你从我的服务器下载<br/><br/>
所以可能你的任务会长时间一直在拉取（尤其是大文件）

### 3.加速效果

个人项目，没钱开很多服务器+宽带。所以我直接加了限制，正常情况下单文件限速300kb/s x 3<br/>
<a>你可以在软件里使用手机登录，登录后限速为600kb/s x 3<a/>。<br/>
有特殊情况:<br/>
* 同时使用的人很多时下载速度会变慢（很少出现，我服务器带宽够大）<br/>
* 不同地区&不同宽带服务商&在不同时间，下载速度会剧烈浮动（这是网络联通问题，我没钱在每个城市开1台服务器）<br/>
* 有的文件使用 百度VIP会员 下载也很慢，应该是百度CDN调度问题 ( 还比较常见，VIP也不是万能的)<br/>
* 有用户提交大体积的分享链接时，其他用户会长期处于拉取中(那就等等吧，我们按照提交链接的顺序去排队下载)<br/>
* 现在并不支持总体积大于 10GB 的分享链接（因为会导致其他人长时间等待）<br/><br/>
* 链接第一次被提交需要解析和缓存，以后第二个人再次提交同样的链接就瞬间秒解了<br/>
* 链接第一次被提交，链接内文件需要等待较长时间拉取和缓存。以后第二个人再次提交同样的链接就直接开始下载了<br/>
* 用户多了我会再加服务器，现在只是测试阶段人很少，服务器也少，拉取可能需要多等等<br/><br/>
   
总之一句话，自己使用使用一下才知道，注意不同时间表现是完全不同的。免费项目，不要找我问为什么你的下载速度慢<br/>

---

#### Q:什么时候会收费？
个人项目，永久免费。没钱我会去寻求捐赠，实在没钱我会关掉项目。所以永远免费。
#### Q:文件版权纠纷?
我们提供了醒目的举报入口，欢迎大家和我们一起维护版权，打击各种违规文件。只要举报，无条件封杀
#### Q:有问题怎么联系？
github上发Issue吧，我会不定时的来看看的，看到了就会回复你
#### Q:会开源吗？用的什么技术？
客户端是c++，用到了SOUI3，SQLite，Curl，GoogleBase，等等，界面都是我自己设计后用PS贴图<br/>
VIP下载端是C# + C++ 混合<br/>
存储端是C#写的上传阿里云OSS + 函数计算（C#）切片<br/>
文件中转端是.net core 3.1 + nginx<br/>
CDN是用的阿里云+边缘规则<br/>
最开始客户端是用的miniblink+vue+curl。不过体积确实太大放弃了<br/>
<br/>
你看，所有的都告诉你了，具体的代码因为是个人项目，又乱又杂，还有一堆BUG。实在羞于出手。等以后项目稳定了会考虑开源客户端C++的部分代码，因为SOUI就是开源的<br/>
