# CSS

Cascading Style Sheet 层叠样式表

### [CSS 选择器](./CSS选择器.md)

### 盒模型

w3c标准盒模型

IE 怪异盒模型

盒模型由 margin border padding content组成

标准盒模型宽高指content的
怪异盒模型指content + padding + border 的

### CSS 如何设置这两种盒模型？

box-sizing: content-box

box-sizing: border-box

### BFC

块级格式化上下文

三点
1.布局规则
5点
内部的box 会在垂直方向上一个接一个地放置
属于同一个bfc的两个相邻的box的margin会发生重叠
bfc是独立元素 内部元素不影响外部 外部同理 才怪 内部文字超长 该出来还是会出来
bfc区域 不会与float box重叠
计算bfc高度 浮动元素也参与计算

2.如何触发  5点
overflow: auto/hidden
display: flow-root inline-block
float: 不为none
html
position absolute fixed

3.作用 两点即可
清浮动
清除文字环绕


### BFC、IFC、GFC 和 FFC

块级
内联
网格
自适应 flex

### 非布局样式

字体 颜色 大小 行高
背景 边框
滚动 换行

### 行高的构成

line-box组成
line-box由一行里的 inline-box组成
inline-box最高的那个 或者字体最大的那个 决定行高


### float

浮动
脱离文档流
不脱离文本流
位置尽量靠上 靠左或右



### 清除浮动

1.BFC
父元素形成BFC 同时设置宽度 不能设置height 
2.伪元素
::content::after {
  display: block;
  content: ' ';
  visibility: hidden;
  height: 0;
  clear: both;
}


### inline-block 的间隙
空格导致
font-size: 0 或去掉空格

### 你对 line-height 是如何理解的？
上一行的基线到下一行的基线
如果没有行高 则由line-height决定高度
line-height=height可以让文字垂直居中


### line-height 三种赋值方式有何区别？（带单位、纯数字、百分比）
纯数字是比例 传给子代使用 子代字体大小乘以比例
百分比同理

### 图片下面有一个缝隙是因为什么
img元素是行内元素 同时属于替换元素 因此可以设置宽高
但是对其方式按行内元素的规则进行
会按基线对齐 缝隙是基线和底线的距离
vertial-align: bottom 或者 display:block即可


### 边框
线型 颜色 大小


### 滚动
overflow: auto; 滚动条自动隐藏
overflow: visible 滚动条隐藏 文字超出显示
scroll 滚动条不隐藏 
hidden 超出不显示 

### 文字折行 回答属性即可 值和区别说不会 
word-wrap break-word normal
word-break
white-space

### 装饰属性及其他
text-decoration
font-style itatic
font-weight
cursor: pointer

### CSS Hack
一部分不合法的语法 在某些浏览器上生效

替代方案 
特征检测
ua 识别以后加特定类名


### 单行文本溢出显示省略号
overflow: hidden;
text-overflow: ellipsis;
white-space: no-wrap;

### 多行文本溢出显示省略号
overflow: hidden;
text-overflow: ellipsis;
display: -webkit-box;
-webkit-line-clamp: 3;
-webkit-box-orient: vertical;

### display: none; 与 visibility: hidden; opacity: 0的区别
display: none 渲染树上不存在 不占位 会触发回流 性能消耗大 点不到
visibility: hidden 渲染树上存在 占位 重绘不回流 性能消耗较小 点不到
opacity 渲染树上存在 占位 可以点击 重绘

js都能获取到

继承性
visibility继承
display: none 不继承 但是父元素没了 子元素也不会显示

### 外边距折叠(collapsing margins)
块级元素的外边距会发生重叠 
均为正数 取较大值
均为负数 绝对值较大值
一正一负 求和

### CSS 单位
px
em 父级元素字体大小
rem 根元素字体大小

% 父元素宽度
vw vh 视口大小


### [transform 变形](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


### CSS 预处理器  说下带来的好处即可
less 
sass
stylus

变量 减少冗余代码
循环 相似有规律的样式
嵌套  显示层级关系
import css模块化


### CSS 优化、提高性能的方法有哪些？
雪碧图
多个css合并 减少http请求 css-loader
提取公共样式 减少代码量
压缩css代码


## [DOM 层级顺序与 z-index](https://segmentfault.com/a/1190000014382426)

### link 与 @import 的区别
link在html文档中使用 rel引用外部样式表
@import在css文件中使用 
多个link会进行并行下载
@import会导致串行下载

@import在老浏览器中无法使用 可以用来做渐进增强 或优雅降级

### CSS 有哪些继承属性


### display 有哪些值？说明他们的作用
flow-root 产生BFC
inline-block
inline
inherit 集成父元素的值


### position 有哪些值？ relative 和 absolute 定位原点是？


### CSS3 新特性？
transform 元素变换
animation 动画
flex 弹性盒
媒体查询
box-shadow
border-radius
text-overflow: ellipsis

### 如何水平居中一个元素？
margin: 0 auto
text-align center


### 用纯 CSS 创建一个三角形的原理是什么？
w3c盒模型中 边框的形状是个梯形
transparant


### li 与 li 之间有看不见的空白间隔是什么原因引起的？有什么解决办法？(也称幽灵字符)
空格


### display:inline-block 什么时候会显示间隙？(携程)
font-size:0;letter-spaceing:-4px;
可能有水平的 也可能有垂直的
行内增加


### 什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的 IE？


### 谈谈浮动和清除浮动


### box-sizing 常用的属性有哪些？分别有什么作用？

### 请列举几种隐藏元素的方法


### rgba() 和 opacity 的透明效果有什么不同？


### css 属性 content 有什么作用？


### 元素竖向的百分比设定是相对于容器的高度吗？


### a 标签上四个伪类的使用顺序是怎么样的？


### 伪元素和伪类的区别和作用？


### ::before 和 :after 中双冒号和单冒号有什么区别？


### 设置元素浮动后，该元素的 display 值会如何变化？


### 请解释 CSS sprites，以及你要如何在页面或网站中实现它


### base64 的使用


### margin 叠加几种情况

