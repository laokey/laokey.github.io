### HTML
  个人整理一些HTML知识，仅供学习参考。
  ___
- 关于 Doctype

  ><!DOCTYPE> 声明必须是 HTML 文档的第一行，位于 <html> 标签之前。     
  ><!DOCTYPE> 声明不是 HTML 标签；它是指示 web 浏览器关于页面使用哪个 HTML 版本进行编写的指令。        
  >在 HTML 4.01 中，<!DOCTYPE> 声明引用 DTD，因为 HTML 4.01 基于 SGML。DTD 规定了标记语言的规则，这样浏览器才能正确地呈现内容。        
  >HTML5 不基于 SGML，所以不需要引用 DTD。

- 浏览器的标准模式和兼容模式

  >标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。
  
- 关于浏览器内核

  >主要分成两部分：渲染引擎(layout engineer或Rendering Engine)和JS引擎。    
  渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器或打印机。
  浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其它需要编辑、显示网络内容的应用程序都需要内核。    
  JS引擎：解析和执行javascript来实现网页的动态效果。    
  最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。   
  常见的浏览器内核：    
  Trident内核：IE,MaxThon,TT,The World,360,搜狗浏览器等。[又称MSHTML]    
  Gecko内核：Netscape6及以上版本，FF,MozillaSuite/SeaMonkey等    
  Presto内核：Opera7及以上。      [Opera内核原为：Presto，现为：Blink;]    
  Webkit内核：Safari,Chrome等。   [ Chrome的：Blink（WebKit的分支）]   
  
- HTML全局属性
  
  >参考资料：[MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes) 、[W3C](http://www.w3school.com.cn/tags/html_ref_standardattributes.asp)    
  >accesskey:设置快捷键，提供快速访问元素如aaa在windows下的firefox中按alt + shift + a可激活元素   
class:为元素设置类标识，多个类名用空格分开，CSS和javascript可通过class属性获取元素    
contenteditable: 指定元素内容是否可编辑    
contextmenu: 自定义鼠标右键弹出菜单内容    
data-*: 为元素增加自定义属性(H5新特性)    
dir: 设置元素文本方向    
draggable: 设置元素是否可拖拽    
dropzone: 设置元素拖放类型： copy, move, link    
hidden: 表示一个元素是否与文档。样式上会导致元素不显示，但是不能用这个属性实现样式效果    
id: 元素id，文档内唯一    
lang: 元素内容的的语言    
spellcheck: 是否启动拼写和语法检查    
style: 行内css样式    
tabindex: 设置元素可以获得焦点，通过tab可以导航    
title: 元素相关的建议信息    
translate: 元素和子孙节点内容是否需要本地化    

- web语义化
  >web语义化是指通过HTML标记表示页面包含的信息，用正确的标签做正确的事情。    
   好处：html语义化让页面的内容结构化，结构更清晰;     
   搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;      
   便于阅读维护理解，便团队项目的可持续运作及维护。  
   
 - HTML5有哪些新特性？HTML与HTML5如何区分？    
   >* 新特性：    
   >1. 语义特性：新增语义标签，这些标签带有一定的语义，使搜索引擎爬取你的网站信息更高效。    
   >2. 本地存储特性：应用程序缓存（App cache），本地存储(Local Storage)，索引数据库(Indexed DB)，文件接口(File API)    
   >3. 设备访问特性：地理位置API（Geolocation API），媒体访问API（media API），设备方向和运动API（DeviceOrientation & DeviceMotion API）    
   >4. 连接特性：Web Sockets，服务器发送事件（Server-Sent Events）    
   >5. 网页多媒体特性：Audio 和 Video 标签    
   >6. 三维、图形及特效特性（3D, Graphics & Effects）:SVG、Canvas、WebGL、CSS3 3D    
   >7. 性能与集成特性：网页后台任务（Web Workers）、XMLHttpRequest 2    
   
   >* 如何区分HTML5： DOCTYPE声明\新增的结构元素\功能元素
   
- 关于 iframe    
  > iframe 元素会创建包含另外一个文档的内联框架（即行内框架）。    
    iframe会阻塞主页面的Onload事件;搜索引擎的检索程序无法解读这种页面，不利于SEO;iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。    
    使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript动态给iframe添加src属性值，这样可以绕开以上两个问题。
    
- 如何实现浏览器内多个标签页之间的通信?    
  >WebSocket、SharedWorker；也可以调用localstorge、cookies等本地存储方式；    
  localstorge另一个浏览上下文里被添加、修改或删除时，它都会触发一个事件，
  通过监听事件，控制它的值来进行页面信息通信；
  
- cookies，sessionStorage 和 localStorage 的区别？    
  > cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）。    
  cookie数据始终在同源的http请求中携带（即使不需要），会在浏览器和服务器间来回传递。    
  sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。    
  >存储大小：    
  	cookie数据大小不能超过4k。    
  	sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。    
  >有期时间：    
  	localStorage    存储持久数据，浏览器关闭后数据不丢失除非主动删除数据；    
  	sessionStorage  数据在当前浏览器窗口关闭后自动删除。    
  	cookie          设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭    
    





