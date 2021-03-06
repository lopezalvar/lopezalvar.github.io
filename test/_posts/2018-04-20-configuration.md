---
layout: post
title: 'Document - Configuration'
key: 20180420
category: Document
tags:
- Document
- English
---

Jekyll allows you to concoct your sites in any way you can dream up, and it’s thanks to the powerful and flexible configuration options that this is possible. These options can either be specified in a `_config.yml` file placed in your site’s root directory, or can be specified as flags for the jekyll executable in the terminal.

For technical reasons, this file is *NOT* reloaded automatically when you use `jekyll serve`. If you change this file, please restart the server process.
{:.warning}

<!--more-->

## Site Settings

### Theme

If you’re using the Ruby gem version of the theme you’ll need this line to activate it:

```yaml
theme: minimal-mistakes-jekyll
```

### Color Theme

You can choose these 6 built-in color themes below:

| `default` | `dark` | `forest` |
| --- |  --- | --- |
| ![default](https://raw.githubusercontent.com/kitian616/jekyll-TeXt-theme/master/screenshots/colors_default.png) | ![dark](https://raw.githubusercontent.com/kitian616/jekyll-TeXt-theme/master/screenshots/colors_dark.png) | ![forest](https://raw.githubusercontent.com/kitian616/jekyll-TeXt-theme/master/screenshots/colors_forest.png) |

| `ocean` | `chocolate` | `orange` |
| --- |  --- | --- |
| ![ocean](https://raw.githubusercontent.com/kitian616/jekyll-TeXt-theme/master/screenshots/colors_ocean.png) | ![chocolate](https://raw.githubusercontent.com/kitian616/jekyll-TeXt-theme/master/screenshots/colors_chocolate.png) | ![orange](https://raw.githubusercontent.com/kitian616/jekyll-TeXt-theme/master/screenshots/colors_orange.png) |

```yaml
text_color_theme: default # "default" (default), "dark", "forest", "ocean", "chocolate", "orange"
```

### URL

The base hostname and protocol for your site. if you are hosting the site on Github Pages this will be set as the GitHub Pages domain (cname or user domain)[^gitHub_metadata]. For example, https://kitian616.github.io or https://tianqi.name if there is cname file.

Jekyll 3.3 overrides this value with url: http://localhost:4000 when running `jekyll serve` in a development environment[^jekyll_site_variables]. You can specifying Jekyll environment[^jekyll_specifying_environment] to production environment by `JEKYLL_ENV=production` to avoid this behavior.
{:.warning}

[^gitHub_metadata]: [GitHub Metadata, a.k.a. site.github](https://github.com/jekyll/github-metadata#what-it-does)

[^jekyll_site_variables]: [Variables#Site Variables](https://jekyllrb.com/docs/variables/#site-variables)

[^jekyll_specifying_environment]: [Configuration#Specifying a Jekyll environment at build timePermalink](https://jekyllrb.com/docs/configuration/#specifying-a-jekyll-environment-at-build-time)

### Base URL

The base URL for your site, default to '/'. If you are hosting the site on Github Pages this will be set as the project name for project pages if none is set[^gitHub_metadata].

### Title

The name of your site.

```yaml
title: "My Awesome Website"
```

### Description

Use some words to describe your site.

```yaml
description: > # this means to ignore newlines until "nav_lists:"
  A website with awesome stories.
```

## Language and Timezone

### Language

The language of your site, you can override it with different ones on specific posts, pages by YAML Front Matter[^font_matter].

| Name | Language |
| --- | --- |
| **en** | English(default) |
| **zh** | Simplified Chinese, 简体中文 |
| **zh-Hans** | Simplified Chinese, 简体中文 |
| **zh-Hant** | Traditional Chinese, 繁體中文 |

```yaml
lang: en
```

[^font_matter]: [Front Matter](https://jekyllrb.com/docs/frontmatter/)

### Timezone

Set the time zone for site generation. This sets the TZ environment variable, which Ruby uses to handle time and date creation and manipulation. A list of all available values can be found [HERE](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

When serving on a local machine, the default time zone is set by your operating system. But when served on a remote host/server, the default time zone depends on the server's setting or location.[^jekyll_global_configuration]

[^jekyll_global_configuration]: [Configuration#Global Configuration](https://jekyllrb.com/docs/configuration/#global-configuration)

```yaml
timezone: Asia/Shanghai
```

## Author and Social

Information of the site author (a person, a team, an organization or even a cat).

### Name

Used to assign a site author.

### Social

Username or id of site author's social networks.

Now we supports Email, Facebook, Twitter, Google Plus, Github, Linkedin, Weibo(微博) and Douban(豆瓣), more to be added.

Depending on your settings, the social network buttons would show on every pages' footer.

## GitHub repository

Setting for [GitHub Metadata](https://github.com/jekyll/github-metadata) plugin, you can refer to [HERE](https://github.com/jekyll/github-metadata/blob/master/docs/configuration.md#configuration) for more info.

In order for jekyll-github-metadata to know what metadata to fetch it must be able to determine the repository NWO (name with owner, e.g. kitian616/jekyll-TeXt-theme) to ask GitHub about.

"NWO" stands for "name with owner." It is GitHub lingo for the username of the owner of the repository plus a forward slash plus the name of the repository, e.g. 'kitian616/jekyll-TeXt-theme', where 'kitian616' is the owner and 'jekyll-TeXt-theme' is the repository name.

```yaml
repository: username/repo-name
```

## Navigation *

Todo ...

## Post

### Excerpt

Each post automatically takes the first block of text, from the beginning of the content to the first occurrence of excerpt_separator, and sets it as the post’s excerpt.

The post's excerpt is show in the articles list in the home layout. There are two excerpt types: text type and html type:

| Type Name | Description |
| --- | --- |
| **text** | the excerpt are plain text that filters out all non-text elements (such as title, link, list, table, picture, etc.) and only show 350 characters most. |
| **html** | the excerpt are HTML document just like the content of the article, This will show all the content by default, except adding `<!--more-->` in the article Markdown file, You can find more info [HERE](https://jekyllrb.com/docs/posts/#post-excerpts).  |

```yaml
excerpt_separator: <!--more-->
excerpt_type: text # text (default), html
```

### TOC

Elements to use as headings.

```yaml
toc:
  selectors: "h1,h2,h3"
```

### Markdown Enhancements

To improve the user experience for both reading and writing posts, TeXt made some enhancements for markdown. By default, all the enhancements for markdown is enabled. you need set the settings to true to enable them:

```yaml
# Mathjax
mathjax: true
mathjax_autoNumber: true

# Mermaid
mermaid: true

# Chart
chart: true
```

And also you can override it with different ones on specific posts, pages by YAML Front Matter[^font_matter].

Check [Writing Posts](/) for detail usage.

## Paginate

Settings for [Jekyll Paginate](https://github.com/jekyll/jekyll-paginate) plugin. to enable pagination for posts on your blog, add a line to the _config.yml file that specifies how many items should be displayed per page:

```yaml
paginate: 8
```

The number should be the maximum number of Posts you’d like to be displayed per-page in the generated site.

You may also specify the destination of the pagination pages:

```yaml
paginate_path: /blog/page:num # don't change this unless for special need
```

## Sources

TeXt use CDN[^cdn] for speed improvements, You can choose [BootCDN](http://www.bootcdn.cn/)(default) or [unpkg](https://unpkg.com/) as your site's CDN provider, both of them are open source and free.

If your website is mainly for Chinese, just use BootCDN.

```yaml
sources: bootcdn # bootcdn (default), unpkg
```

[^cdn]: [Content delivery network](https://en.wikipedia.org/wiki/Content_delivery_network)

## Comments

| Name | Comment Provider |
| --- | --- |
| **disqus** | [Disqus](https://disqus.com/) |
| **gitalk** | [Gitalk](https://github.com/gitalk/gitalk/) |

### disqus

To use Disqus you’ll need to create an account and [shortname](https://help.disqus.com/customer/portal/articles/466208-what-s-a-shortname-). Once you have both update _config.yml to:

```yaml
disqus:
  shortname: "your-disqus-shortname"
```

### gitalk

To use gitalk you need a GitHub application, if you don't have one, [Click here to register](https://github.com/settings/applications/new) a new one. and then update _config.yml to:

```yaml
gitalk:
  clientID: "github-application-client-id"
  clientSecret: "github-application-client-secret"
  repository: "github-repo"
  owner: "github-repo-owner"
  admin: # Github repo owner and collaborators, only these guys can initialize github issues, IT IS A LIST.
    - "your-github-id"
    - "other-admin-github-id"
```

## Pageview

TeXt use [LeanCloud](https://leancloud.cn/) as back-end service. You need create a app on the dashboard, and config the app's id, key and class name.

The detail guide of LeanCloud will find in Chinese document(not available yet) since LeanCloud haven't provide an English-language edition.
{:.info}

```yaml
leancloud:
  app_id: "your-leanCloud-app-id"
  app_key: "your-leanCloud-app-key"
  app_class: "your-leanCloud-app-class"
```

## Analytics

### Google Analytics

In order to use Google Analytics, set `ga_tracking_id` to your Google Analytics tracking code.

```yaml
ga_tracking_id: "your-google-analytics-tracking-code"
```