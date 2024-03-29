# 1、HTML 基础问题

### 1. 前端需要注意哪些 SEO

* 合理的 `title` `description` `keywords`: 搜索对这三项的权重**逐个减小**， `title` 强调重点即可，重要关键词出现不超过 2 次，而且要靠前， 不同页面要有不同的 `title` ； `description` 高度概括页面内容，长度合适，不可过分堆砌关键词，不同页面 `description` 应该不同； `keywords` 列举出关键词即可
* 语义化的 `HTML` 代码，符合 W3C 规范： 语义化代码让搜索引擎容易理解网页
* 重要内容 `HTML` 代码放在前面，便于引擎抓取
* 重要内容不适用 `js` 输出： 搜索引擎不和执行 js 代码获取内容
* 少用 `iframe` : 搜索引擎不会抓取 `iframe` 中的内容
* 非装饰性图片必须添加 `alt`
* 提高网站速度： 网站速度是搜索引擎排序的一个重要指标

### 2.  \<img\> 的 title 和 alt有什么区别

* `title` ：当鼠标移动至图片时显示
* `alt` ：当图片无法被加载时，代替图片显示

### 3. 语义化的理解

* 用正确的标签做正确的事情
* `HTML` 语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析
* 在没有样式的情况下也能以文档的形式展示，而且容易阅读
* 有利于 SEO
* 使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解

### 4. iframe 有哪些缺点

* `iframe` 会阻塞主页面的 `onload` 事件
* 搜索引擎的检索程序无法理解这种页面，不利于 SEO
* `iframe` 和主页面共享连接池，而浏览器对相同域的链接有限制，所以会影响页面的并行加载

### 5. 重绘和重排(回流)

* DOM 的变化影响到了元素的几何属性（宽高），浏览器计算元素集合属性，其他元素集合属性和位置也会收到影响，这个过程称为 回流 （重排）
* 浏览器只是将属性值改变的元素重新绘制到屏幕上的过程称为重绘
* 引起重排（回流）的原因有以下几点
  * 添加或者删除可见的DOM元素
  * 元素位置、尺寸、内容改变
  * 浏览器页面初始化
  * 浏览器窗口改变
  * 修改display造成重排，修改visibility造成重绘
* 减少重绘和重排的方法
  * 不在布局信息改变时做DOM查询
  * 使用`className` 一次性改变属性
  * 使用 `fragment`
  * 对于多次重排的元素，使用绝对定位脱离文档流

