# 前端面试题个人小结

1.谈谈对css模型的理解
CSS模型分为标准盒content-box  ,怪异盒模型border-box
都由4部分组成 margin padding conten border 
怪异盒模型最主要的特点是 padding和border的值不会影响到 主盒子已设定好的宽度和高度

2.设置浮动后父元素高度塌陷  怎么解决
（1）直接给父元素添加高度
（2）在子元素最后加一个带有clear：both的空div clear清浮动
（3）给父元素增加一个overflow-hidden
（4）使用：after伪元素

3.说几个设置位置宽高元素水平垂直居中方式
（1）flex弹性布局  justfly-content:center align-items:center
（2）Grid 网格布局
（3）设置绝对定位absolute left50% top50% 以及transform translate(高度和宽度的-50%)

4.说一下H5和CSS3新增了那些东西
（1）H5语义化标签 header footer nav main section aside等  避免使用无意义的标签 使代码具有可读性
（2）H5在表单（input）方面，增加了color（颜色）、email（邮箱）、data、range等类型；
（3）在存储方面，提供了Sessionstorage、localStorage和离线存储、通过这些方式， 方便数据的存储和获取
（4）在多媒体方面，新增了音频和视频元素，audio和vedio
CSS方面
1.边框：border-radius（圆角边框）、box-shadow（盒子阴影）等；
2.背景图：background-size（图片大小）、background-origin等；
3. 2D、3D的转换transform等；
4.动画animation等；

5.H5的本地存储
Cookie localStorage sessionStorage
Cookie一般用于存储登录验证信息或者token，LocalStorage常用于存储不易变动的数据，减轻服务器的压力，SessionStorage可以用来检测用户是否是刷新进入页面 关闭浏览器就没了
cookie由服务器写入 sessionStorage以及localStorage都是由前端写入

6.对于闭包的理解
闭包 是 函数里面再定义函数 这样就形成了一个闭包 这个内部函数可以访问外部作用域函数的变量 并且如果外部函数不暴露这个内部函数的话 那么外界就不知道这个内部函数的存在 它只能在自己的内部函数使用
并且内部的函数可以作为返回值返回出去 这样整个外部函数就形成一个高阶函数 也就是返回函数的一个函数 
闭包的好处是可以给高阶函数里面的变量设置只读属性 这样外界只能访问它的值而不能修改它的值 从而起到了保护作用 缺点闭包引用另外一个函数的活动对象,因此这个活动对象无法被销毁，所以闭包比一般的函数需要更多的内存消耗

7.Ajax的原理
ajax的工作原理就是通过XmlHttpRequest对象来向服务器发出异步请求,从服务器中获得数据,然后用Javascript来操作DOM从而更新局部页面。
（1）创建Ajax对象(XmlHttpRequest)
（2）判断数据的传输方式（get/post）
（3）打开连接open()
（4）发送send()

8.跨域是什么 怎么解决跨域问题
（1）跨域是指浏览器的同源策略是不允许执行其他网站上的脚本，只要协议，主机地址，端口其中之一不同就算跨域
（2）跨域一般的解决方法
1.Jsonp，script标签不受同源策略影响 
src属性指向没有跨域限制 但是存在安全隐患 不适用于vue和react ；
2.后端可以设置cros
3.前端开发环境中配置代理中转请求 因为跨域是浏览器的保护机制 如果脱离了浏览器发送请求 那么久不会受到跨域保护的影响 可以配置proxy 对/api路径代理转发到真实的后端服务路径再根据需要对转发的url进行改写
4.node中间件、nginx反向代理：跨域限制的时候浏览器不能跨域访问服务器，node中间件和nginx反向代理，都是让请求发给代理服务器，静态页面面和代理服务器是同源的，然后代理服务器再向后端服务器发请求，服务器和服务器之间不存在同源限制。

9.nginx是什么
是一个高性能的HTTP和反向代理web服务器
1，反向的含义是：代表外部网络用户向内部服务器发出请求，拿到响应返回给外部用户。(外到内)
2，那么正向代理就是：代表内部网络用户向外部服务器发出连接请求，拿到响应返回给内部用户。(内到外)
3，反向代理服务器位于用户与目标服务器之间，反向代理服务器通常可用来作为Web加速，即使用反向代理作为Web服务器的前置机来降低网络和服务器的负载，提高访问效率。



