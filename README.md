### WatcherOne.github.io
***

- [ ] 🤔 This is watcher's blog repository
- [x] 😄 [在线浏览](https://watcherone.github.io/)
- [x] 🎃 Follow Me

***

> #### 创建 GitHub Pages 网站

&nbsp;&nbsp;&nbsp; ➊ 新建储存库，输入 `username.github.io` 作为存储库名称，`username` 为你的 `GitHub用户名` <br/>
&nbsp;&nbsp;&nbsp; ➋ 在存储库下，单机 `settings` <br/>
&nbsp;&nbsp;&nbsp; ➌ 在边栏 `Pages` 中，在 `Build and deployment` 的 `Source` 下选择 `Deploy from a branch` <br/>
&nbsp;&nbsp;&nbsp; ➍ 然后在 `Branch`[^1] 下选择对应的分支 <br/>
&nbsp;&nbsp;&nbsp; ➎ 访问 `username.github.io` 以查看新网站 <br/>
&nbsp;&nbsp;&nbsp; ➏ 如果想通过 GitHub Pages 访问其它仓库，*则须将对应仓库按上述进行设置（无需改仓库名）*<br/>
&nbsp;&nbsp;&nbsp; ➐ 访问 `username.github.io/newRepository` 以查看该仓库对应的网站<br/>

[^1]: master分支

> #### 更改标题和说明

&nbsp;&nbsp;&nbsp; ➊ 站点标题默认为 `username.github.io`<br/>
&nbsp;&nbsp;&nbsp; ➋ 可通过配置储存库中的 `_config.yml` 文件来修改<br/>
&nbsp;&nbsp;&nbsp; ➌ 设置`title`修改标题，`description` 修改描述<br/>

```yml
title: watcher's blog
subtitle: subtitle
description: some description for website
keywords: github pages blog
author: watcher
language: zh-CN
theme: fluid
```

- node 16.14.0
