### CSS
  个人整理的一些CSS知识，仅供学习参考。
___

- 简要介绍盒子模型
  > CSS盒子模型又称框模型 (Box Model) ，包含了元素内容（content）、内边距（padding）、边框（border）、外边距（margin）几个要素。     
  > 分为两种类型：IE盒子模型、W3C盒子模型，区别是IE的content部分把 border 和 padding计算了进去;

- CSS选择器有哪些，哪些可以继承？
  > * 常用选择器：    
    1.id选择器（ # myid）    
  	2.类选择器（.myclassname）    
  	3.标签选择器（div, h1, p）    
  	4.相邻选择器（h1 + p）    
  	5.子选择器（ul > li）    
  	6.后代选择器（li a）    
  	7.通配符选择器（ * ）    
  	8.属性选择器（a[rel = "external"]）    
  	9.伪类选择器（a:hover, li:nth-child）  
    > * 可继承的样式： font-size font-family color, UL LI DL DD DT;    
    > * 不可继承的样式：border padding margin width height ;  
- CSS 优先级算法
  > 优先级就近原则，同权重情况下样式定义最近者为准;    
  > 优先级：    
  >  同权重: 内联样式表（标签内部）> 嵌入样式表（当前文件中）> 外部样式表（外部文件中）。    
  >	!important >  id > class > tag    
  >	important 比 内联优先级高

- 页面导入样式时，使用link和@import有什么区别？
  > link属于XHTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;        
  页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;    
  import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;

- css sprite是什么,有什么优缺点
  > 概念：将多个小图片拼接到一个图片中。通过background-position和元素尺寸调节需要显示的背景图案。    
  >优点：减少HTTP请求数，极大地提高页面加载速度；
   增加图片信息重复度，提高压缩比，减少图片大小；
   更换风格方便，只需在一张或几张图片上修改颜色或样式即可实现    
  > 缺点：图片合并麻烦；维护麻烦，修改一个图片可能需要从新布局整个图片，样式

- display: none;与visibility: hidden;的区别
  >联系：它们都能让元素不可见    
  >区别：
  > 1. display:none;会让元素完全从渲染树中消失，渲染的时候不占据任何空间;       visibility: hidden;不会让元素从渲染树消失,渲染时元素继续占据空间，只是内容不可见。
  > 2. display: none;是非继承属性，子孙节点消失由于元素从渲染树消失造成，通过修改子孙节点属性无法显示；visibility:hidden;是继承属性，子孙节点消失由于继承了hidden，通过设置visibility: visible;可以让子孙节点显式
   > 3. 修改常规流中元素的display通常会造成文档重排。修改visibility属性只会造成本元素的重绘。

- PNG,GIF,JPG的区别及如何选?
  > GIF:8位像素，256色,无损压缩,支持简单动画,支持boolean透明,适合简单动画    
  > PNG:有PNG8和truecolor,PNG8类似GIF颜色上限为256，文件小，支持alpha透明度，无动画,适合图标、背景、按钮    
  > JPG:颜色限于256,有损压缩,可控制压缩质量,不支持透明,适合照片

- CSS3有哪些新特性
  > 新增各种CSS选择器	（: not(.input)：所有 class 不是“input”的节点）    
    圆角		    （border-radius:8px）    
    多列布局	    （multi-column layout）        
    阴影和反射	（Shadow\Reflect）   
    文字特效		（text-shadow、）   
    文字渲染		（Text-decoration）   
    线性渐变		（gradient）   
    旋转		 	（transform）   
    缩放,定位,倾斜,动画,多背景   

- position跟display、margin collapse、overflow、float这些特性相互叠加后会怎么样？
  > 如果元素的display为none,那么元素不被渲染,position,float不起作用    
  如果元素拥有position:absolute;或者position:fixed;属性那么元素将为绝对定位,float不起作用.    
  如果元素float属性不是none,元素会脱离文档流,根据float属性值来显示.    
  有浮动,绝对定位,inline-block属性的元素,margin不会和垂直方向上的其他元素margin折叠.

- 外边距折叠(collapsing margins)
  > 外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。

- CSS优化、提高性能的方法有哪些？
  > 关键选择器（key selector）。选择器的最后面的部分为关键选择器（即用来匹配目标元素的部分）；    
  如果规则拥有 ID 选择器作为其关键选择器，则不要为规则增加标签。过滤掉无关的规则（这样样式系统就不会浪费时间去匹配它们了）；    
  提取项目的通用公有样式，增强可复用性，按模块编写组件；增强项目的协同开发性、可维护性和可扩展性;    
  使用预处理工具或构建工具（gulp对css进行语法检查、自动补前缀、打包压缩、自动优雅降级）；

- 请解释一下为什么需要清除浮动？清除浮动的方式
  > 清除浮动是为了清除使用浮动元素产生的影响。浮动的元素，高度会塌陷，而高度的塌陷使我们页面后面的布局不能正常显示。    
  > 容器元素闭合标签前添加额外元素并设置clear: both    
   父元素触发块级格式化上下文(见块级可视化上下文部分)    
   设置容器元素伪元素进行清理推荐的清理浮动方法。

- 什么是CSS 预处理器 / 后处理器？
  >预处理器例如：LESS、Sass、Stylus，用来预编译Sass或less，增强了css代码的复用性，还有层级、mixin、变量、循环、函数等，具有很方便的UI组件模块化开发能力，极大的提高工作效率。

  >后处理器例如：PostCSS，通常被视为在完成的样式表中根据CSS规范处理CSS，让其更有效；目前最常做的是给CSS属性添加浏览器私有前缀，实现跨浏览器兼容性的问题。





  