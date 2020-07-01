### 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？
行内 span input select img i em strong b
块 div aside main h1 p ul li ol
空 meta link br hr img

### 页面导入样式时，使用 link 和@import 有什么区别？
多个link会并发请求 @import串行
低版本浏览器不支持@import语法
link是html标签 @import是css语法

### 介绍一下你对浏览器内核的理解？
两个线程
gui js线程
一个运行 另一个挂起

### HTML5 变化
语义化标签
存储 localstorage sessionstorage indexdb
websocket
canvas 
video audio

### property 和 attribute 的区别
attribute是html标签的属性 设置了 当使用getAttribute获取时不会因为property变化而变化

### 主流浏览器机器内核
ie trident
opera blink
chrome chromiun blink
safari 

### 简述一下你对 HTML 语义化的理解？
利于SEO
利于设备解析时确定该区域作用 例如阅读器遇见语法标签会重读
利于代码管理