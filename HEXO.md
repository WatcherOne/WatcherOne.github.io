#### Blog-hexo Code

> ###### 文件解构说明

```javascript
|--- _config.yml    // 网站的配置信息
|--- package.json   // 应用程序信息，相关依赖配置
|--- scaffolds      // 模版文件夹，当您新建文章时，Hexo 会根据 scaffold 来创建文件
|--- source         // 资源文件夹是存放用户资源的地方
|                   // 除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略
|                   // Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去
|--- themes         // 主题文件夹，Hexo会根据主题来生成静态页面
```

1. 新增文章
> Hexo有三种默认布局：post、page、draft
> 使用不同布局会将生成的文件放到不同路径
> post  -> source/_posts
> page  -> source/page
> draft -> source/_drafts // 是特殊布局，即草稿，草稿不会显示在页面中
                          // 但可以预览或 publish 命令 移动到 source/_posts中
> 可以在config中禁用布局

```shell
# layout - 设置模板文件夹（即scaffolds中的文件）
# 不设置时，默认 config.yml 中的 default_layout 参数代替
hexo new [-p xx/xx] [-r] [layout] <title>
# -p === --path 指定新文章路径，如果不指定会根据文章标题来生成，一般是文章标题为文件夹+index.md
# -r 如果存在同名文章，将其替换
```

2. 模板参数 Front-matter
```shell
## 文件最上方以 ‘---’ 分隔区域
## 模板中可以获取文章中这些变量值
---
layout:         # 布局，默认 config.default_layout
title:          # 标题，文章的文件名
date:           # 建立日期，文章的建立日期
updated:        # 更新日期，文章的更新日期
comments：      # 开启文章的评论功能，默认 true
tags:           # 标签（不适用于分页）
categories:     # 分类（不适用于分页）
                # categories: 
                #   - Diary
                # tags:
                #   - PS3
                #   - Games
---
```

3. 标签插件
> [详细内容](https://hexo.io/zh-cn/docs/tag-plugins)
```shell
- 可以插入方言，引用
- 可以插入代码块、图片、链接
- 可以插入视频等。
```

4. 资源文件夹
> 一般 markdown 引用图片等资源，是关联地址
> 就是通过创建一个文件夹存放地址，如 source/images 文件夹
> Hexo 提供了更组织化的方式管理，设置 config.yml 中 post_asset_folder: true
> 此时，通过 Hexo 命令创建文章时，同时会自动创建一个资源文件夹（会有和文章文件一样的名称）
> 通过 markdown ![]() 这种 也被 标签插件代替， 相对路径引用的标签插件

5. 数据文件
> [详细内容](https://hexo.io/zh-cn/docs/data-files)
> source/_data 中的 json 或 yaml 文件中的数据可以重复用于模板中
```html
<% for (var link in site.data.menu) { %>
  <a href="<%= site.data.menu[link] %>"> <%= link %> </a>
<% } %>
```

6. 启动服务器
```shell
# 默认情况下，访问网址为： http://localhost:4000/
hexo server
```

7. 生成静态文件
```shell
# -d === --deploy   文件生成后立即部署网站
# -w === --watch    监听文件变动
# -f === --force    强制重新生成文件
hexo [-d] [-w] [-f] generate
hexo g  # 简写
```

8. 部署文件
```shell
hexo deploy  # 部署项目前，必须要生成文件
hexo deploy --generate   # 生成完毕后自动部署
hexo d -g    # 简写
```