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
&nbsp;&nbsp;&nbsp; ➏ 对于访问某些仓库文件夹内的html时，需要将分支后 /(root) 换成 /docs【才能进入到文件夹里面】<br/>
&nbsp;&nbsp;&nbsp; ➐ 访问 `username.github.io/newRepository` 以查看该仓库对应的网站<br/>

[^1]: master分支

> #### 启动项目注意点

- node 16.14.0（对应版本问题）
- 部署生成的项目在 gh-pages 分支（要使有作用，在.github中加一些配置文件）
- 其实就是 在 gp-pages 分支 部署生成对应的 最外层 index.html 文件
- 通过插件将public里面的文件上传到 对应分支中（还不是很能理解）
- 固设置 github 存储库时的 Source 时要选择 gh-pages 分支
- Todo：应该是可以在 master 分支上直接部署到 gh-pages 分支的！！！
