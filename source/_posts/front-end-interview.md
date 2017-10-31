---
title: 前端面试题大全
date: 2017-10-15 15:11:06
tags: web manage
---

Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).


+ 请描述一下 cookies，sessionStorage 和 localStorage 的区别？
  > cookie在浏览器和服务器间来回传递。 sessionStorage和localStorage不会
  > sessionStorage和localStorage的存储空间更大；
  > sessionStorage和localStorage有更多丰富易用的接口；
  > sessionStorage和localStorage各自独立的存储空间

+ 如何实现浏览器内多个标签页之间的通信? 
  > 调用localStorage、cookies等本地存储方式
  
+ css 块级元素  a
  > div,p,h1,form,ul,li;

+ CSS隐藏元素的几种方法 
  > Opacity:元素本身依然占据它自己的位置并对网页的布局起作用。它也将响应用户交互;
  > Visibility:与 opacity 唯一不同的是它不会响应任何用户交互。此外，元素在读屏软件中也会被隐藏;
  > Display:display 设为 none 任何对该元素直接打用户交互操作都不可能生效。此外，读屏软件也不会读到元素的内容。这种方式产生的效果就像元素完全不存在;
  > Position:不会影响布局，能让元素保持可以操作;
  > Clip-path:clip-path 属性还没有在 IE 或者 Edge 下被完全支持。如果要在你的 clip-path 中使用外部的 SVG 文件，浏览器支持度还要低; 

+ Flex布局
  > 解释一下


+ 对于SASS或是Less的了解程度？喜欢那个？
  > 语法介绍
  
+ CSS3新增伪类有那些？
  > :nth:child()
  > first:child()

+ 数组方法pop() push() unshift() shift()
  > 解释一下

+ ajax请求的时候get 和post方式的区别?  a
  > 一个在url后面 一个放在虚拟载体里面
  > 有大小限制
  > 安全问题
  > 应用不同 一个是论坛等只需要请求的，一个是类似修改密码的;

+ call和apply的区别 
  > Object.call(this,obj1,obj2,obj3)
  > Object.apply(this,arguments)

+ ajax请求时，如何解释json数据?
  > 使用eval parse,鉴于安全性考虑 使用parse更靠谱;
   
+ 事件委托是什么?
  > 让利用事件冒泡的原理，让自己的所触发的事件，让他的父元素代替执行！
  
+ 闭包是什么，有什么特性，对页面有什么影响?简要介绍你理解的闭包
  > 闭包就是能够读取其他函数内部变量的函数。
  
+ 添加 删除 替换 插入到某个接点的方法
  ```javascript
  let obj;
  obj.appendChidl()
  obj.innersetBefore()
  obj.replaceChild
  obj.removeChild
  ```


+ 说一下什么是javascript的同源策略？
  > 一段脚本只能读取来自于同一来源的窗口和文档的属性，这里的同一来源指的是主机名、协议和端口号的组合

+ 编写一个b继承a的方法;
  ```javascript
  function A(name){
      this.name = name;
      this.sayHello = function(){alert(this.name);};
  }
  function B(name,id){
      this.temp = A;
      this.temp(name);        //相当于new A();
      delete this.temp;       
       this.id = id;   
      this.checkId = function(ID){alert(this.id==ID)};
  }
  ```

+ 如何阻止事件冒泡和默认事件
  ```javascript
    function stopBubble(e)
    {
        if (e && e.stopPropagation)
            e.stopPropagation();
        else
            window.event.cancelBubble=true
    }
    return false
  ```


+ 下面程序执行后弹出什么样的结果? 
    ```javascript
    function fn() {
        this.a = 0;
        this.b = function() {
            alert(this.a)
        }
    }
    fn.prototype = {
        b: function() {
            this.a = 20;
            alert(this.a);
        },
        c: function() {
            this.a = 30;
            alert(this.a);
        }
    };
    var myfn = new fn();
    myfn.b();
    myfn.c();
    ```

+ 谈谈This对象的理解
  > this是js的一个关键字，随着函数使用场合不同，this的值会发生变化。
  > 但是有一个总原则，那就是this指的是调用函数的那个对象。
  > this一般情况下：是全局对象Global。 作为方法调用，那么this就是指这个对象+


+ 对于前端自动化构建工具有了解吗？简单介绍一下
  > gulp,webpack

+ 介绍一下你了解的后端语言以及掌握程度
  > node
  > python
  > mysql
  > shell

+ 你有哪些性能优化的方法？
  > 减少http请求次数：CSS Sprites, JS、CSS源码压缩、图片大小控制合适；网页Gzip，CDN托管，data缓存 ，图片服务器。
  > 前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存AJAX请求结果，每次操作本地变量，不用请求，减少请求次数
  > 用innerHTML代替DOM操作，减少DOM操作次数，优化javascript性能。
  > 当需要设置的样式很多时设置className而不是直接操作style。
  > 少用全局变量、缓存DOM节点查找的结果。减少IO读取操作。
  > 避免使用CSS Expression（css表达式)又称Dynamic properties(动态属性)。
  > 图片预加载，将样式表放在顶部，将脚本放在底部 加上时间戳。
  > 避免在页面的主体布局中使用table，table要等其中的内容完全下载之后才会显示出来，显示div+css布局慢。对普通的网站有一个统一的思路，就是尽量向前端优化、减少数据库操作、减少磁盘IO。向前端优化指的是，在不影响功能和体验的情况下，能在浏览器执行的不要在服务端执行，能在缓存服务器上直接返回的不要到应用服务器，程序能直接取得的结果不要到外部取得，本机内能取得的数据不要到远程取，内存能取到的不要到磁盘取，缓存中有的不要去数据库查询。减少数据库操作指减少更新次数、缓存结果减少查询次数、将数据库执行的操作尽可能的让你的程序完成（例如join查询），减少磁盘IO指尽量不使用文件系统作为缓存、减少读写文件次数等。程序优化永远要优化慢的部分，换语言是无法“优化”的。

+ http状态码有那些？分别代表是什么意思？
  > 100-199 用于指定客户端应相应的某些动作。
  > 200-299 用于表示请求成功。
  > 300-399 用于已经移动的文件并且常被包含在定位头信息中指定新的地址信息
  > 400-499 用于指出客户端的错误。400 1、语义有误，当前请求无法被服务器理解。401 当前请求需要用户验证 403 服务器已经理解请求，但是拒绝执行它。
  > 500-599 用于支持服务器错误。 503 – 服务不可用
  
+ 一个页面从输入 URL 到页面加载显示完成，这个过程中都发生了什么？（流程说的越详细越好）
  > 查找浏览器缓存
  > DNS解析、查找该域名对应的IP地址、重定向（301）、发出第二个GET请求
  > 进行HTTP协议会话
  > 客户端发送报头(请求报头)
  > 文档开始下载
  > 文档树建立，根据标记请求所需指定MIME类型的文件
  > 文件显示
  > 浏览器这边做的工作大致分为以下几步：
  > 加载：根据请求的URL进行域名解析，向服务器发起请求，接收文件（HTML、JS、CSS、图象等）。
  > 解析：对加载到的资源（HTML、JS、CSS等）进行语法解析，建议相应的内部数据结构（比如HTML的DOM树，JS的（对象）属性表，CSS的样式规则等等）


+ 简述一下src与href的区别?
  > href 是指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，用于超链接。
  > src是指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；在请求src资源时会将其指向的资源下载并应用到文档内，
  > 例如js脚本，img图片和frame等元素。当浏览器解析到该元素时，会暂停其他资源的下载和处理，直到将该资源加载、编译、执行完毕，
  > 图片和框架等元素也如此，类似于将所指向资源嵌入当前标签内。这也是为什么将js脚本放在底部而不是头部

+ 简述同步和异步的区别
  > 同步是阻塞模式，异步是非阻塞模式。 同步就是指一个进程在执行某个请求的时候，若该请求需要一段时间才能返回信息，
  > 那么这个进程将会一直等待下去，直到收到返回信息才继续执行下去； 异步是指进程不需要一直等下去，
  > 而是继续执行下面的操作，不管其他进程的状态。当有消息返回时系统会通知进程进行处理，这样可以提高执行的效率。

+ px和em的区别
  > px和em都是长度单位，区别是，px的值是固定的，指定是多少就是多少，计算比较容易。em得值不是固定的，
  > 并且em会继承父级元素的字体大小。 浏览器的默认字体高都是16px。
  > 所以未经调整的浏览器都符合: 1em=16px。那么12px=0.75em, 10px=0.625em

+ 数组去重[4]
  ```ecmascript 6
  var arr1 =[1,2,2,2,3,3,3,4,5,6],
      arr2 = [];
  for(var i = 0,len = arr1.length; i&lt; len; i++){
      if(arr2.indexOf(arr1[i]) &lt; 0){
          arr2.push(arr1[i]);
      }
  }
  document.write(arr2); 
  ```
+ 在Javascript中什么是伪数组？如何将伪数组转化为标准数组？
  > 伪数组（类数组）：无法直接调用数组方法或期望length属性有什么特殊的行为，
  但仍可以对真正数组遍历方法来遍历它们。典型的是函数的argument参数，
  还有像调用getElementsByTagName,document.childNodes之类的,它们都返回NodeList对象都属于伪数组。
  可以使用Array.prototype.slice.call(fakeArray)将数组转化为真正的Array对象。
  ```ecmascript 6
  function log(){
        var args = Array.prototype.slice.call(arguments);  
        args.unshift('(app)');
        console.log.apply(console, args);
  };
  ```


+ Javascript中callee和caller的作用？
  > caller是返回一个对函数的引用，该函数调用了当前函数；callee是返回正在被执行的function函数，也就是所指定的function对象的正文。

+ 一次完整的HTTP事务是怎样的一个过程？
  > 基本流程： a. 域名解析 b. 发起TCP的3次握手 c. 建立TCP连接后发起http请求 d. 服务器端响应http请求，浏览器得到html代码 e. 浏览器解析html代码，并请求html代码中的资源 f. 浏览器对页面进行渲染呈现给用户

+ 你所了解到的Web攻击技术
  > （1）XSS（Cross-Site Scripting，跨站脚本攻击）：指通过存在安全漏洞的Web网站注册用户的浏览器内运行非法的HTML标签或者JavaScript进行的一种攻击。 
  > （2）SQL注入攻击 
  > （3）CSRF（Cross-Site Request Forgeries，跨站点请求伪造）：指攻击者通过设置好的陷阱，强制对已完成的认证用户进行非预期的个人信息或设定信息等某些状态更新。

+ JSON 的了解？js对象和json对象一样么？
  > 不一样

+ 哪些常见操作会造成内存泄漏？
  > 内存泄漏指任何对象在您不再拥有或需要它之后仍然存在。
　　垃圾回收器定期扫描对象，并计算引用了每个对象的其他对象的数量。如果一个对象的引用数量为 0（没有其他对象引用过该对象），或对该对象的惟一引用是循环的，那么该对象的内存即可回收。
　　setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏。
　　闭包、控制台日志、循环（在两个对象彼此引用且彼此保留时，就会产生一个循环）。


+ 线程与进程的区别
  > 一个程序至少有一个进程,一个进程至少有一个线程。
　　线程的划分尺度小于进程，使得多线程程序的并发性高。
　　另外，进程在执行过程中拥有独立的内存单元，而多个线程共享内存，从而极大地提高了程序的运行效率。
　　线程在执行过程中与进程还是有区别的。每个独立的线程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。
　　从逻辑角度来看，多线程的意义在于一个应用程序中，有多个执行部分可以同时执行。但操作系统并没有将多个线程看做多个独立的应用，来实现进程的调度和管理以及资源分配。这就是进程和线程的重要区别。


+ 什么是promise？





+ 
  