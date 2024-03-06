---
title: 常用工具网站
# 文章摘要
excerpt: 一些常用的网页在线工具或者一些前端插件，包括一些工具网站
date: 2023-08-01 08:15:30
index_img: /imgs/website/index_img.png
banner_img: /imgs/website/banner_img.jpg
banner_img_height: 35
sticky: 1000
tags:
    - 工具
---

<style>
table th:first-of-type {
    min-width: 120px;
}
table th:nth-of-type(2) {
    width: 40%;
}
table th:nth-of-type(3) {
    width: 60%;
}
</style>

> 网址工具类

| 地址   | 描述 | 补充 |
| :---: | ------ | -------- |
| [qr](https://link-to-qr.com/) | 一款在线制作二维码图 | 可以自定义url以及二维码样式颜色 |
| [svg](https://editor.method.ac/) | 一款在线制作 svg 图 | 可以导入图片编辑也可以选择一些形状等 |
| [flex](https://the-echoplex.net/flexyboxes/) | 一款在线可视化Flex布局效果实时展示 | 利于新手学习 |
| [svg插图](https://undraw.co/) | 一个提供svg插图素材的网站 | 用于下载一些svg格式的素材 |
| [API](https://overapi.com/) | 一个汇聚了大量开发语言和工具的API | 用于快速查看API文档,只有常用的 |
| [正则表达式](https://ihateregex.io/) | 一个提供常用正则表达式的网站 | 可以修改正则来验证 |
| [css-dev](https://cssbattle.dev/) | 一个针对CSS爱好者的代码高尔夫游戏网站 | 以用最小的CSS代码直观地还原题目 |

> 工具插件类

| 地址   | 描述 | 补充 |
| :---: | ------ | -------- |
| [print](https://printjs.crabbly.com/) | 一款打印pdf插件 | 未使用过 |

> chrome浏览器插件

| 地址   | 描述 | 补充 |
| :---: | ------ | -------- |
|  |  | 允许用户自定义脚本 |

<table>
    <thead>
        <tr>
            <th>地址</th>
            <th>描述</th>
            <th>补充</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>[Tampermonkey](https://printjs.crabbly.com/)</td>
            <td>油猴,用于安装与管理脚本的插件</td>
            <td>允许用户自定义脚本</td>
        <tr>
        <tr>
            <td colspan="3">[全网VIP视频](chrome-extension://dhdgffkkebhmkfjojejmpbldmpobfkfo/ask.html?aid=1518a3ca-e7ed-4c49-8bef-362959e2d5fc)</td>
        </tr>
    </tbody>
</table>

> 娱乐类

| 地址   | 描述 | 补充 |
| :---: | ------ | -------- |
| [虚拟号码](https://sms-activate.org) | 外网虚拟号码服务平台 | 通过虚拟号码接收短信验证码 [详细](https://WatcherOne.github.io/2023/08/01/websiteVirtualPhone) |
| [盗版游戏A](https://byrutdb.org) | `Byrutor`盗版游戏下载 | 一款来自俄罗斯的破解游戏资源网站 [详细](https://WatcherOne.github.io/2023/08/01/websiteGameALoad) |
| [盗版游戏B](https://rutracker.net) | `RuTracker`盗版游戏下载 | 俄罗斯此前最大的的盗版资源下载网站 [详细](https://WatcherOne.github.io/2023/08/01/websiteGameBLoad) |
| [盗版游戏C](https://download.fourpetal.com) | `Switch520`盗版游戏下载 | 国内游戏下载网址，提供很多switch游戏 [详细](https://WatcherOne.github.io/2023/08/01/websiteGameCLoad) |
| [openAI-官网](https://openai.com) | openAI公司官网 | 测试账号: `谷歌账号` / `密码大写`  |
| [openAI-chat](https://chat.openai.com) | chatGPT-chat网站 | 人工智能对话，需要翻墙 |
| [openAI-doc](https://platform.openai.com) | openAI平台文档说明 | 提供用户登录等API文档，常用示例说明，需要翻墙+无痕 |
| [openAI-api](https://api.openai.com) | api服务地址 | 提供后端接口的服务器，需要翻墙+无痕 |


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
