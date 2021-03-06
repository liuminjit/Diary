## Diary

#December 8, 2016

###Cookie 快速理解

Cookie就是服务器暂存放在你计算机上的一份记录（文件），好让服务器用来辨认你的计算机

当你在浏览网站的时候，Web服务器会发送并保存一份记录（文件）放在你的计算机上

Cookie 会帮你在网站上所打的文字或是一些选择，都记录下来。当下次你再访问同一个网站

Web服务器会先看看有没有它上次留下的Cookie资料，有的话，就会依据Cookie里的内容来判断使用者并送出特定的网页内容给你

Cookie的使用很普遍，许多提供个人化服务的网站都是利用Cookie来辨认使用者，以方便送出使用者量身定做的内容

像是Web接口的免费E-mail网站，都要用到 Cookie

Cookie中记载的资料相有限，Cookie是安全的

网站不可能经由Cookie获得你的E-mail地址或是其它私人资料，更没有办法透过Cookie来存取你的计算机

但是如果你实在不喜欢Web服务器乱丢饼干(Cookie)到你的计算机，当然可以让浏览器拒绝网站存放Cookie到你的计算机

只要在IE的“工具”菜单下选择“Intertnet选项”的“安全”，按自定义级别，将Cookie部分设为关闭，按确定，关闭浏览器，再重新启动浏览器即可

当你关闭Cookie之后，很多网站的个人化服务功能很可能也不能再使用了

#December 9, 2016

###Python 爬虫入门

爬虫是一门很优秀的技术，给我的感觉就是可以用很简单的逻辑实现很强大的功能。

这里说一下Python爬虫的明确的逻辑：

从网页上抓取数据大致分三步

1.模拟浏览器访问，获取HTML源代码

2.通过正则匹配获得标签中的一些内容

3.将获取到的内容写到文件中

而后我们可以拥有一些扩展：

4.将我们收集到的信息生成数据报告，进行数据分析，生成图表等东西

5.生成EXE文件，使其可以直接执行

6.生成图形化界面，使其用户体验更友好

感谢让我入门并成功执行的网址
>http://blog.csdn.net/bo_wen_/article/details/50868339

#December 12, 2016

###JavaScript 笔记
因为网景开发了JavaScript，一年后微软又模仿JavaScript开发了JScript，为了让JavaScript成为全球标准，几个公司联合ECMA（European Computer Manufacturers Association）组织定制了JavaScript语言的标准，被称为ECMAScript标准。

所以简单说来就是，ECMAScript是一种语言标准，而JavaScript是网景公司对ECMAScript标准的一种实现。

最新版ECMAScript 6标准（简称ES6）已经在2015年6月正式发布

JavaScript严格区分大小写，如果弄错了大小写，程序将报错或者运行不正常

这个特殊的Number与所有其他值都不相等，包括它自己：  NaN === NaN; // false

唯一能判断NaN的方法是通过isNaN()函数：  isNaN(NaN); // true

#December 13, 2016

###Bug修正思路
这是一个判断方法。
当首次点击某个链接时候，正常跳转，并记录特定值Id和Name.

结论-**正常执行请求后跳转并赋新值**.

当第二次点击时-判断特定值，若传入值Id是相等，Name相等，则不请求遍历搜索直接跳转。

结论-**直接跳转**.

当第二次点击时-判断特定值，若传入值Id不相等，Name相等，例如-经营一部.

结论-**正常执行请求后跳转并赋新值**.

当第二次点击时-判断特定值，若传入值Id是相等，Name不等, 例如-财务部和财务部下的项目组.

结论-**正常执行请求后跳转并赋新值**.

当第二次点击时-判断特定值，若传入值Id是不等, Name不等，例如-开发部和财务部.

结论-**正常执行请求后跳转并赋新值**.

目的，**减少对于服务器的请求数**。

此处注意点 

1.注意判断的过程，和赋值的顺序，可以用console.log进行判断传值

2.判断是否Id和Name能否当主键，判断是否有相同的Id 或者是相同的Name

####修正
以上判断可以归纳为： 如果Id 和Name 都相等的时候，就可以直接进行跳转，而其他情况就全部为else的情况

#December 14, 2016

### gulp 入门

首先安装**nodejs**,然后通过nodejs的**npm全局安装**和**项目安装gulp**,其次在项目里安装所需要的**gulp插件**,然后新建gulp的配置文件**gulpfile.js**并写好配置信息（定义gulp任务）,最后通过**命令提示符**运行gulp任务即可。

安装nodejs -> 全局安装gulp -> 项目安装gulp以及gulp插件 -> 配置gulpfile.js -> 运行任务

#December 26, 2016

### Session 快速理解

Session是服务器端使用的一种记录客户状态的机制。使用上比Cookie简单一些，相应的也增加了服务器的存储压力。

#December 27, 2016

### SessionStorage 、 localstorage 和 cookie 之间的区别

共同点是：都是保存在**浏览器端**，且**同源**的。

cookie数据始终在同源的**http请求**中携带（即使不需要），**即cookie在浏览器和服务器间来回传递**

而sessionStorage和localStorage不会自动把数据发给服务器，**仅在本地保存**

#### 从大小上来看
cookie数据还有路径（path）的概念，可以限制cookie只属于某个路径下。

存储大小限制也不同，cookie数据不能超过**4k**，同时因为每次http请求都会携带cookie，所以cookie只适合保存很小的数据，如会话标识

sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，**可以达到5M或更大**。

#### 从有数据有效期来看

sessionStorage：仅在**当前浏览器窗口关闭前有效**，自然也就不可能持久保持；

localStorage：**始终有效**，窗口或浏览器关闭也一直保存，因此用作持久数据；

cookie只在设置的cookie**过期时间**之前一直有效，即使窗口或浏览器关闭。

#### 从共享角度来看

作用域不同，sessionStorage**不在不同的浏览器窗口中共享**，即使是同一个页面；

localStorage 在所有同源窗口中**都是共享的**；

cookie也是在所有同源窗口中**都是共享的**。

Web Storage 支持事件通知机制，可以将数据更新的通知发送给监听者。Web Storage 的 api 接口使用更方便。

#December 28, 2016

### JSON.stringify 语法实例

作用：这个函数的作用主要是为了系列化对象的。 

就是说把原来是对象的类型转换成字符串类型（或者更确切的说是json类型的）

JSON.stringify()，这是ECMAScript5新增的方法

如果不使用JSON.stringify()函数的话，alert一个对象会出现object .简单的说就是把object里面的内容取出来

JSON.stringify()可以拥有三个参数，第一个就是你输入的对象，可以是数组 可以是对象，可以是类。

第二个参数可以是方法可以是数组，如果是方法，将第一个参数中的所有都放进方法里，如果是数组，会过滤不再数组里的属性

第三个参数可以是数字，也可以是字符串，数字代表缩进字符的空格数。 也可以是转义字符，/t是回车，如果是字符串也会在显示在每行前（最大是10个字符）

参考文章地址：http://www.jb51.net/article/29893.htm
