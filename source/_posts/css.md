---
title: CSS知识积累
# 文章摘要
excerpt: CSS的常见面试考点，以及CSS汇集的知识点
date: 2023-08-22 09:00:00
index_img: /imgs/website/index_img.png
banner_img_height: 35
tags:
    - CSS
category:
    - 前端面试
    - CSS
---

<style>
.text-highlight {
    color: #e19832;
}
.text-keynote {
    color: #333;
    font-weight: bold;
}
.text-mark {
    background-color: #efd4af;
    padding: 0 0.4em 0.2em;
    font-size: 90%;
    border-radius: 3px;
}
.text-star {
    color: #e53030;
    font-size: 150%;
    font-weight: bold;
    vertical-align: middle;
    line-height: 20px;
}
.content-box {
    border: 1px solid #dfe2e5;
    background-color: #f6f8fa;
    padding: 10px 10px 10px 20px;
    margin-bottom: 15px;
    border-radius: 5px;
}
.content-box .order {
    color: #428bca;
    font-size: 18px;
    font-weight: bold;
}
.post-content .markdown-body blockquote {
    background-color: #f6f6f6;
    padding: 0.3em 1em;
    border-left-color: #428bca;
    font-size: 95%;
}
</style>

### 盒子模型的理解

<style>
.markdown-body table:first-of-type th:first-of-type {
    min-width: 120px;
}
</style>

<div class="content-box">
    <span class="order">1.</span> 当对一个文档进行布局时，浏览器的渲染引擎会根据标准之一的CSS基础框盒模型<br/>
    <span class="order">2.</span> 将所有元素表示为一个个<span class="text-highlight">矩形的盒子</span><br/>
    <span class="order">3.</span> 标准包括：<span class="text-keynote">标准模型</span> + <span class="text-keynote">怪异模型</span><br/>
    <span class="order">4.</span> 盒子由: 
        <span class="text-mark">content</span> +
        <span class="text-mark">padding</span> +
        <span class="text-mark">border</span> +
        <span class="text-mark">margin</span> 组成<br/>
</div>

- padding：内边距，清除内容周围的区域，取值**不能为负值**！<br/>
- margin:  外边距，在元素外创建额外的空白，**可以为负值**！

<p class="note note-success">标准模型：W3C标准盒子模型，浏览器默认的盒子模型</p>

- 盒子总宽度 = width + padding + border + margin
- 盒子总高度 = height + padding + border + margin

<p class="note note-success">怪异模型：IE怪异盒子模型</p>

- 盒子总宽度 = width + margin
- 盒子总高度 = height + margin
- 也就是说 width/height 包含了 padding 和 border 值

<p class="note note-success">box-sizing属性</p>

> 定义了引擎应该如何计算一个元素的总宽度和总高度

| 属性值 | 描述 |
| :---: | ----- |
| content-box | 默认值，元素 `width/height 不包含 padding,border` 与标准盒子模型表现一致 |
| border-box | 元素 `width/height 包含 padding,border` 与怪异盒子模型表现一致 |
| inherit | 指定 box-sizing 属性值 从父元素继承 |


### BFC的理解 Todo

> Block Formatting Context: 块级格式化上下文，它是页面上的一块渲染区域，并且有一套自己的渲染规则

<div class="content-box">
    <span class="order">1.</span> 内部的盒子会在垂直方向上一个接一个的放置<br/>
    <span class="order">2.</span> 对于同一个BFC的俩个相邻的盒子的margin会发生重叠，与方向无关<br/>
    <span class="order">3.</span> 每个元素的左外边距与包含块的左边界相接触（从左到右）<br/>
    <span class="order">4.</span> BFC区域不会与float的元素区域重叠<br/>
    <span class="order">5.</span> 计算BFC的高度时，浮动子元素也参与计算<br/>
    <span class="order">6.</span> BFC就是页面上一个隔离的独立容器，容器内的子元素不会影响到外面的元素！<br/>
</div>

> BFC 目的就是形成一个相对于外界完全独立的空间，让内部子元素不会影响到外部的元素

<p class="note note-success">触发条件</p>

- A...

<p class="note note-success">应用场景</p>

- 防止 margin 重叠（塌陷）
- 清除内部浮动（在BFC中计算高度时，浮动元素也会参入则浮动元素就不会重叠）

### CSS选择器

> CSS选择器是 CSS规则的第一部分
> <span class="text-star">*</span> 表示 `CSS3` 新增的

<p class="note note-success">基础选择器</p>

- <span class="text-mark">ID选择器</span>
- <span class="text-mark">类选择器</span>
- <span class="text-mark">标签选择器</span>
- <span class="text-mark">后代选择器</span>（#box div）：选择ID为box元素的内部所有div元素
- <span class="text-mark">子选择器</span>（#box > div）：选择父元素为ID为box元素的所有div元素（只有父子关系）
- <span class="text-mark">相邻同胞选择器</span>（#box + .two）：选择紧接ID为box元素之后的一个 .two 元素（相邻的）
- <span class="text-mark">群组选择器</span>（div,p）：选择div，p的所有元素
- <span class="text-star">*</span> <span class="text-mark">层次选择器 / 通用兄弟选择器</span>（p ~ ul）： 选择P元素后面的所有兄弟元素ul

<p class="note note-success">伪类选择器</p>

- <span class="text-mark">:link</span>         选择未被访问的链接
- <span class="text-mark">:visited</span>      选择已被访问的链接
- <span class="text-mark">:active</span>       选择活动链接
- <span class="text-mark">:hover</span>        选择鼠标指针浮动在上面的元素
- <span class="text-mark">:focus</span>        选择具有焦点的元素
- <span class="text-mark">:first-child</span>  选择父元素的首个子元素（本身元素必须是第一个元素）

| 伪类选择器 |  描述 |
| :---:  |  ------  |
| <span class="text-mark">:link</span>    | 选择未被访问的链接 |
| <span class="text-mark">:visited</span> | 选择已被访问的链接 |
| <span class="text-mark">:active</span>  | 选择活动链接 |
| <span class="text-mark">:hover</span>   | 选择鼠标指针浮动在上面的元素 |
| <span class="text-mark">:focus</span>   | 选择具有焦点的元素 |
| <span class="text-mark">:first-child</span>  | 选择父元素的首个子元素（本身元素必须是第一个元素） |
| <span class="text-star">*</span> <span class="text-mark">:checked</span> |  |
| <span class="text-star">*</span> <span class="text-mark">:disabled</span> |  |
| <span class="text-star">*</span> <span class="text-mark">:enabled</span> |  |
| <span class="text-star">*</span> <span class="text-mark">:empty</span> |  |
| <span class="text-star">*</span> <span class="text-mark">:root</span> |  |
| <span class="text-star">*</span> <span class="text-mark">:not(selector)</span> |  |
| <span class="text-star">*</span> <span class="text-mark"></span> |  |
| <span class="text-star">*</span> <span class="text-mark"></span> |  |
| <span class="text-star">*</span> <span class="text-mark"></span> |  |
·          选择选中的元素
·         选择被禁用的元素
·          选择可用的元素（与disabled互斥的，默认的输入框就是enabled）
*            选择没有子元素的元素（子元素包括内容为空）
·             表示文档根元素，相当于全局属性，常用来定义CSS变量
·    选择与 selector 不匹配的所有元素，有用++

        * of-type:::  ！！对于标签和className是不同含义的
        * type        ！！类型一定指的是标签
        · :first-of-type   选择父元素的第一个同种类型的子元素（本身元素必须是同种类型中的第一个元素）
        · :last-child      选择父元素的最后一个子元素（最后一个子元素必须是当前元素）
        · :last-of-type    选择父元素的同种类型的最后一个子元素
        · :nth-child(n)    选择元素在一组同级中的位置匹配元素（n从1开始的正整数，an + b, 可以 odd even）
        . :nth-of-type(n)  选择元素在一组同级中相类型元素的匹配位置
        · :only-child      选择没有任何兄弟的元素
        · :only-of-type    选择没有同类型兄弟元素的元素


### 响应式布局的理解 Todo
### 水平垂直居中的方法 Todo
### 多栏布局，固定与自适应 Todo

<div id="gitalk-container"></div>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.css">
<script src="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.min.js"></script>

<script>
const gitalk = new Gitalk({
    clientID: '3e6a50fe69c43e59de05',
    clientSecret: '829d07fcd6cc13e98928a3dd207758cda7c4facb',
    repo: 'WatcherOne.github.io',
    owner: 'WatcherOne',
    admin: ['WatcherOne'],
    id: location.pathname,
    distractionFreeMode: false
})

gitalk.render('gitalk-container')
</script>
