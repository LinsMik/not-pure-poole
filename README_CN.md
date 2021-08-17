# Not Pure Poole <!-- omit in toc -->

<a href="https://jekyll-themes.com">
  <img src="https://img.shields.io/badge/featured%20on-JekyllThemes-red.svg" height="20" alt="Jekyll Themes Shield" >
</a>

**Not Pure Poole**是一种简单优美又强大的Jekyll博客主题。它基于 [Poole](https://github.com/poole/poole) 和 [Pure](https://purecss.io/).


> Poole解释道Jekyll已经在寻找一种特殊的化学品一段时间了，每当有了吸引他的东西的时候，他总是以不够**纯粹**拒绝。Poole同样认为他曾在里面瞥见了那个人，而这个人又不那么的像人。
>
> -- <a href="https://www.bbc.co.uk/bitesize/guides/zbtjnrd/revision/6"><cite>Jekyll之死</cite></a>
上面是作者引用的一句话。这个故事里的主人公由于追求去发现并摧毁自己的黑暗人格，用药物引出后又沉迷于变成这个人格，而后被副人格压制，最终惨死的故事。

-----

用这个链接来看Not Pure Poole的效果 [demo站点](https://vszhub.github.io/not-pure-poole/).

![Screenshot](screenshot.png)

## 内容列表 <!-- omit in toc -->

- [特征](#features)
- [安装](#installation)
- [使用](#usage)
  - [配置](#configuration)
  - [自定义标题](#customizing-head)
  - [创建主题](#creating-themes)
  - [自定义导航](#customizing-navigation)
  - [自定义封面图](#customizing-cover-image)
  - [自定义友链](#customizing-social-links)
  - [Enabling Posts Archive](#enabling-posts-archive)
  - [开启TOC](#enabling-toc)
  - [开启MathJax](#enabling-mathjax)
  - [更多](#something-more)
- [开发](#development)
- [许可](#license)

## 特征

- [Jekyll SEO TAG标签](https://github.com/jekyll/jekyll-seo-tag)
- [Jekyll Feed订阅](https://github.com/jekyll/jekyll-feed)
- [Jekyll Sitemap网站地图](https://github.com/jekyll/jekyll-sitemap)
- [Jekyll Gist通用搜索树](https://github.com/jekyll/jekyll-gist)
- [Google Analytics谷歌解析](https://analytics.google.com/)
- [Disqus评论](https://disqus.com/)
- [Font Awesome图标字体库](https://fontawesome.com/)
- [MathJax公式编辑器](https://www.mathjax.org/)
- 深色模式 (enabled automatically via CSS media query)
- 文章用日期、种类和标签归档
- 页码, 由 [Jekyll Paginate](https://github.com/jekyll/jekyll-paginate)生成
- TOC (由Vladimir "allejo" Jimenez's [jekyll-toc](https://github.com/allejo/jekyll-toc)生成)
- 在每个文章下 (由于Jekyll的关系，是基于时间排序的) 显示最近的文章
- 对于移动设备友好的开发和设计
- 文本易于扩展并且内容由CSS的`rem`单元进行计数
- 支持全部的HTML要素
- 语法高亮，颜色美观 (基于Python的代码段高亮器)

## 安装

你可以选择以下方式中的一种来安装Not Pure Poole:

- 直接引入 `not-pure-poole` 装饰.

    1. 添加 `gem 'not-pure-poole'` 到 `Gemfile`.
    2. 将下列语句添加到你的 `_config.yml`.

        ```yml
        plugins:
          - not-pure-poole
        ```

- 如果你的站点放在GitHub Pages, 你可以使用 [`jekyll-remote-theme`](https://github.com/benbalter/jekyll-remote-theme) 来引入Not Pure Poole的主分支.

    1. 添加 `gem 'jekyll-remote-theme'` 到 `Gemfile`.
    2. 将下列语句添加到你的 `_config.yml`.

        ```yml
        plugins:
          - jekyll-remote-theme

        remote_theme: vszhub/not-pure-poole
        ```

## 使用

你可以阅读 [示例文章](https://vszhub.github.io/not-pure-poole/2020/09/29/welcome-to-not-pure-poole/) 来看这个主题的效果, 然后把 [源码](_posts/2020-09-29-welcome-to-not-pure-poole.md) 放到一边来学习如何使用。

### 配置

[`_config.yml`](_config.yml) 在这个仓库里的这个文件已经更改了一些东西，你可以试着在你的仓库中改写它

### 自定义标题

Not Pure Poole留了一个占位符来允许自定义标题，原则上来说，你可以把任何东西加上去，比方说网站图标。你需要做的只有创建一个文件 `_includes/custom-head.html` 然后把你的数据放进去

### 创建主题

如果你想制作自己的颜色主题，从`_sass/_variables.scss`使用域内的数据属性或类名称，更改CSS样式表。

比方说，下面我们来从头创建一个蓝色主题:

```scss
// Example blue theme
[data-theme="blue"] {
  --body-bg: var(--blue);
  --body-color: #fff;
}
```

接下来通过添加`data-theme="blue"` to the `<html>` 元素来应用主题。

### 自定义导航

你可以创建一个文件 `_data/navigation.yml` 来配置一些页面的链接。比方说

```yml
- title: Blog
  url: /
- title: About
  url: /about/
```

### 自定义封面图片

你可以通过修改 `cover_image`文件来自定义你的封面图片，同时也要修改 `_config.yml`，通过设置每个页面的`cover_image`变换，你也可以在不同页面设置不同的封面图片

如果你发现封面背景颜色和文字颜色的对比不够强烈，你可以修改这两个变量:

```yml
cover_bg_color: rgb(40, 73, 77)
cover_color: rgb(255, 255, 255)
```

### 自定义友链

你可以在 `_data/social.yml`设置你自己的链。你可以自定义标题，URL和图标(目前只支持[Font Awesome](https://fontawesome.com/) )，例如:

```yml
- title: Email
  url: mailto://vszhub@gmail.com
  icon: fas fa-envelope
- title: Twitter
  url: https://twitter.com/vszhub
  icon: fab fa-twitter
- title: GitHub
  url: https://github.com/vszhub/not-pure-poole
  icon: fab fa-github
```

### 开启文章分类

Not Pure Poole支持用日期、种类和标签进行文章分类。要开启它，你应该像下面一样向 `_data/archive.yml`中放一些数据:

```yml
- type: dates
  title: Dates
  url: /dates/
- type: categories
  title: Categories
  url: /categories/
- type: tags
  title: Tags
  url: /tags/
```

之后，分类页面的导航应该就出现在主页上方了。

然后，你可以创建一个类型分类的页面，并在该页面设置下列参数:

```yml
---
layout: archive-taxonomies
type: categories
---
```

或者一个标签分类页面:

```yml
layout: archive-taxonomies
type: tags
```

或者一个日期分类页面:

```yml
layout: archive-dates
```

### 开启 TOC

如果你想在页面右侧展示TOC，只需要设置该页面`toc: true`.

### 开启 MathJax

如果你想在网页中写数学公式，只要设置该页面 `math: true`就能开启Mathjax。

### 更多

 **入侵**到源码里面看看你能得到什么 

## 开发

为了建立你对这个主题的开发环境，运行`bundle install`。

你的主题会像一个普通的Jekyll网站建立起来！要测试你的主题，运行`bundle exec jekyll serve` 并打开你的浏览器输入 `http://localhost:4000`。这样使用你的主题的Jekyll服务器就开启了。添加页面、文档、数据等等的，像平常一样测试你的主题内容。当你在对你的主题和内容进行修改的时候，你的站点会重启并且你应该会在浏览器刷新后看到更改生效，就像平时一样。

当你的主题发布是，只有在`_layouts`, `_includes`, `_sass` 和 `assets` 的Git跟踪文件会被捆绑在一起。
要添加一个自定义的你的主题想到，请正确的编辑 `not-pure-poole.gemspec` 中的正则表达式。

## 许可
该主题遵循MIT开源协议 [MIT License](https://opensource.org/licenses/MIT).
