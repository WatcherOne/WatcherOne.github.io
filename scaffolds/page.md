---
# 只是一个模板，只是说以此模板来生成 source 中的 md 文档
# 如下配置并不会启作用！！！
title: {{ title }}
date: {{ date }}
tags:
categories:    # 分类具有顺序性和层次性
hide: false    # 是否隐藏文章，不在首页和其他分类里展示，可通过文章链接查看
index_img:     # 文章在首页的封面图，在 source 目录下，/img/example.png，可外部链接
banner_img:    # 文章首页的顶部大图
sticky:        # 文章靠前的序号
comment: false # 开启评论，boolean 来控制开关，comment: 'valine' 来选择插件
---

<!-- 
只针对当前 fluid 主题配置

标签：（可选 label: primary default info success warning danger）
1. {% note success %}
     文字 或者 `markdown` 均可
   {% endnote %}
2. <p class="note note-primary">标签</p>
上述是换行标签，下面是行内标签
1. {% label primary @text %}
2. <span class="label label-primary">Label</span>

勾选框
{% cb text, checked?, incline? %}

1. text: 显示的文字
2. checked： 是否勾选，默认false
3. incline:  是否内联

按钮
{% btn url, text, title %}
<a class="btn" href="url" title="title">text</a>

1. url：跳转链接
2. text：显示的文字
3. title：鼠标悬停时显示的文字（可选）

组图：将多张图片按一定布局组合显示
-->
