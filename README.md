**MUI** 是一个移动终端的轻量级前端类库，由我在支付宝无线事业部工作时创建的。

这个库诞生的很伟大，但死的却很窝囊。
最之初的 <http://m.alipay.com> 使用的是jquery，那时是2010年，整个移动开发领域还没有一个称得上靠谱的前端框架，
为了快速完成需求，无奈之举，我们使用了pc版本的jquery做 <http://m.alipay.com> 的基础框架，
就这样第一版本的触屏手机站点上线了，pd、老板都很happy，但有洁癖的我却表现的并不开心，为什么不开心？为性能！

jquery在pc市场无疑是最受欢迎的前端类库，使用简单、功能强大、文件轻巧、
插件丰富，只有你想不到的，没有在网上找不到的jquery插件、文档丰富、生态圈也已经形成，总之它就是那么那么的完美，
但在移动领域，以上说的几个优点全是浮云！`jquery min`版本光体积就有近100kb，在2.5g网络加载它简直就是蜗牛！
再严重点，我们就是在杀用户！用户白花花的银子购买的流量，只要访问支付宝触屏站点，过不久就收到运营商的流量超限提醒，
尼玛用户要知道是我干的，Ta不赶到杭州找我算账才怪呢！这是加载方面的性能问题！另外jquery提供的那一大堆功能，
在手机端开发时你常用的也就那几个，`dom、event、animate、utilities`，反正我就是用到这几个方法，
你用到几个我不管，一般wap页面交互都比较简单，不可能复杂的像pc的交互那样，所以我想你也顶不过用三，五个常用的功能，
所以最后为了项目快速上线，我们就狠心、冒着被杀的风险引入了jquery，然后我把注释里的工程师信息都删除了，
怕用户来杭州找我麻烦！还有我想要的功能jquery却没有，比如`touch event`，因此我还是省不掉基于jquery写了一个`touch event plugin`，
就连最后出来的jquery mobile还是基于jquery的插件！而且还带了一坨ui库！jquery在移动端的市场远远不如pc的市场，这也验证了那
帮创业者常常自我安慰的话：pc市场大的产品在移动互联网市场未必，因为这是全新的领域，所有玩家都在同一个起跑线上。

以上就是我为什么不开心，直到 **MUI** 诞生前我一直都不开心，我和pd、pm沟通我为什么不开心，可是每次沟通过后，他们只会
让我更加的不开心，我一直希望用户能够打电话投诉支付宝手机站点太慢了、太耗流量了，可是我期望出现的那些用户却一直未浮出水面，
我必须让自己开心、于是乎我整出一份简单的性能数据找pd、pm沟通，并强调自己的观点：必须要起升级包，解决这个庞大的类库加载问题，
坚持了很久，终于说服他们，我给出解决方案，方案就是自己写一个简单的类库满足当前业务需求。最终达成共识。

这个简单的类库就是 **MUI** ，它非常简单，我们当时就开发了一些项目中常用到的功能，
如`touch event、dom、event、animate、foreach`等工具方法，在具体实现这些功能的时候，我们想到了两个原则：

* 学习成本尽可能的降低再降低，最好是0
* 保证项目轻松从jquery切换至 **MUI** 

抚今追昔，我们的 **MUI** 原则真是牛逼、绝对正确的方向！

因为遵守这两个原则，我们设计 **MUI** 的api时，100％兼容jquery，保证入参、出参与`jquery`一样，
因此甚至有很多核心代码直接从`jquery`中copy的，当然我们要
全力关注移动端的实现，避免重复造轮子，有现成的，就直接拿来用。就这样，一个礼拜后 **MUI** 就诞生了，它的出现解决了移动端
加载资源过大的问题，使`m.alipay.com`在手机端的响应更快(当然由于技术原因，一直没有拿到靠谱的数据)

为什么说死的窝囊，后来因为`m.alipay.com`的需求越来越复杂，加之前端资源的严重缺乏，很多需求都是朝令夕改的， **MUI** 实在
满足不了业务需求，但又没有人负责新功能的开发，于是我们又冒着被用户砍死的风险把jquery引入了，现在看来这是非常傻的决定，
我们应该继续开发 **MUI** ，资源不足的问题不应该与 **MUI** 的开发扯上联系，资源永远都是不足的！

最后zepto发布后，我们表示极度后悔，因为zepto做的事情就是 **MUI** 做的事情，一模一样的思想、一模一样的原则，

现在`(2013-05-24)`m.alipay.com站点使用的是zepto，而 **MUI** 在github的服务器里睡大觉呢，可能永远不会醒来了，它只存活了6个月....

另外 **MUI** 是`mobile user interface` 的简称，当时我们学习`yui`的取名，后来发现雷军做的小米`os`也叫 **MUI** ，这是巧合的同时，也是一种

没有远见的表现，因为当时我取这个名字的时候，还真想到以后会不会有人做个OS或者移动端的什么玩意，也会取个MUI或者MOS之类的东西 :-)。

现在每当我用zepto时，我就会想起 **MUI** 
