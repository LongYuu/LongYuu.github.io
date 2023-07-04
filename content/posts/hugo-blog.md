---
title: "Hugo Blog"
subtitle: ""
date: 2023-06-27T00:42:44+09:00
draft: false
author: Yu Long
categories: ["Blog"]
tags: ["go"]
featuredImage: "/images/hugo_blog/blogging.png"
featuredImagePreview: "/images/hugo_blog/hugo.png"
hiddenFromHomePage: false
hiddenFromSearch: false
---
[Hugo](https://gohugo.io/) is a Static Site Generator(SSG) based on Go, and it support to convert Markdown to HTML. It's easy to use, and simple enough to build your own website. 

<!--more-->

## 1 Installation {#installation}
Just use one simple command, the environment is all set. 
```bash
brew insall hugo                     // MacOS
winget install Hugo.Hugo.Extended    // Windows
sudo apt install hugo                // Linux - Debian (Ubuntu)
sudo dnf install hugo                // Linux - Fedora (CentOS)
```

And you can use the commands it provides to build your site, 
| Command | Description |
|---------|-------------|
| `hugo version` | Check the version of hugo | 
| `hugo new site <siteName>` | Build a new website | 
| `hugo server` | Serving the site on localhost:1313 | 
| `hugo` | Build the site， publishing the files to "public" dir for deployment | 

but beforehand you must be insterested in choosing a [theme](https://themes.gohugo.io/) of your blog. Since I'm using [LoveIt](https://themes.gohugo.io/themes/loveit/), I will take this as an example. 
```bash
git init
git submodule add https://github.com/dillonzq/LoveIt.git themes/LoveIt
```
Accordingly, the configuration needs to be changed to use the theme as well, 
```toml
# theme
theme = 'LoveIt'
```

## 2 Directory {#directory}
After building a new site we can inspect the directories it created, 
```Bash
<newSite>
 ├─archetypes        --> Markdown templates
 │  └─default.md     --> By default, how Hugo creates new content 
 ├─assets            --> All the files need be processed by Hugo Pipes
 │  ├─images
 │  ├─js
 │  └─css
 ├─content           --> Website contents
 ├─data              --> Condiguration files when generating website
 ├─layouts           --> Templates specify how views of content will be rendered
 ├─public            --> Deployment
 ├─resources         --> Caches some files to speed up generation
 ├─static            --> Store all the static content
 ├─themes            --> Pre-built themes
 │  └─LoveIt
 └─hugo.toml         --> Configuration

```

## 3 HomePage {#homepage}
Home page style is totally based on the configurations
```toml
# Home page config
[params.home]
  # amount of RSS pages
  rss = 10
  # Home page profile
  [params.home.profile]
    enable = true
    # Gravatar Email for preferred avatar in home page
    gravatarEmail = ""
    # URL of avatar shown in home page
    avatarURL = "/images/avatar.jpg"
    # title shown in home page (HTML format is supported)
    title = ""
    # subtitle shown in home page (HTML format is supported)
    subtitle = "This is My Blog"
    # whether to use typeit animation for subtitle
    typeit = true
    # whether to show social links
    social = true
    # disclaimer (HTML format is supported)
    disclaimer = ""
  # Home page posts
  [params.home.posts]
    enable = true
    # special amount of posts in each home posts page
    paginate = 6
    # default behavior when you don't set "hiddenFromHomePage" in front matter
    defaultHiddenFromHomePage = false
```

### Header
```toml
# Header config
[params.header]
  # desktop/mobile header mode ["fixed", "normal", "auto"]
  desktopMode = "fixed"
  mobileMode = "auto"
  # Header title config
  [params.header.title]
    # URL of the LOGO
    logo = ""
    # title name
    name = "Yu Long"
    # you can add extra information before the name (HTML format is supported), such as icons
    pre = ""
    # you can add extra information after the name (HTML format is supported), such as icons
    post = ""
    # whether to use typeit animation for title name
    typeit = false
```
The header title will be placed on the left side of the header. On the right side, we have navigation bar if you config the settings, 
```toml
# Menu config
[menu]
  [[menu.main]]
    weight = 1
    identifier = "bio"
    pre = ""
    post = ""
    name = "Bio"
    url = "/bio/"
    title = ""
  [[menu.main]]
    weight = 2
    identifier = "posts"
    pre = ""
    post = ""
    name = "Posts"
    url = "/posts/"
    title = ""
  [[menu.main]]
    weight = 3
    identifier = "tags"
    pre = ""
    post = ""
    name = "Tags"
    url = "/tags/"
    title = ""
  [[menu.main]]
    weight = 4
    identifier = "categories"
    pre = ""
    post = ""
    name = "Categories"
    url = "/categories/"
    title = ""
```

### Footer
```toml
# Footer config
[params.footer]
  enable = true
  # custom content (HTML format is supported)
  custom = ''
  # whether to show Hugo and theme info
  hugo = true
  # whether to show copyright info
  copyright = true
  # whether to show the author
  author = true
  # Site creation time
  since = 2021
  # license info (HTML format is supported)
  license = '<a rel="license external nofollow noopener noreffer" href="https://creativecommons.org/licenses/by-nc/4.0/" target="_blank">CC BY-NC 4.0</a>'
```

## 4 SubPage {#subpage}
There are two kinds of subpage, **section** is used for posts and **list** is used for tags or categories. 

### Posts
The hugo command line tool will help you to create a post really fast, 
| Command | Description |
|---------|-------------|
| `hugo new posts/<postTitle>.md` | create postTitle.md under the folder content/posts |

```toml
# Section (all posts) page config
[params.section]
  # special amount of posts in each section page
  paginate = 20
  # date format (month and day)
  dateFormat = "01-02"
  # amount of RSS pages
  rss = 10
```
For each of the post, 
```toml
# Page global config
[params.page]
  # whether to hide a page from home page
  hiddenFromHomePage = false
  # whether to hide a page from search results
  hiddenFromSearch = false
  # whether to enable twemoji
  twemoji = false
  # whether to enable lightgallery
  lightgallery = false
  # whether to enable the ruby extended syntax
  ruby = true
  # whether to enable the fraction extended syntax
  fraction = true
  # whether to enable the fontawesome extended syntax
  fontawesome = true
  # whether to show link to Raw Markdown content of the content
  linkToMarkdown = true
  # whether to show the full text content in RSS
  rssFullText = false
  # Table of the contents config
  [params.page.toc]
    # whether to enable the table of the contents
    enable = true
    # whether to keep the static table of the contents in front of the post
    keepStatic = false
    # whether to make the table of the contents in the sidebar automatically collapsed
    auto = false
  # social share links in post page
  [params.page.share]
    enable = true
    Twitter = true
    HackerNews = true
    Reddit = true
```
There are lots of link is support to share, including Twitter, Facebook, Linkedin, Whatsapp, Pinterest, Tumblr, HackerNews, Reddit, VK, Buffer, Xing, Line, Instapaper, Pocket, Filpboard, Weibo, Blogger, Baidu, Odnoklassniki, Evernote, Skype, Trello, Mix.

### Tags
We can add tags for each post, and hugo will categorize all the posts by their tag,
```toml
# List (category or tag) page config
[params.list]
  # special amount of posts in each list page
  paginate = 20
  # date format (month and day)
  dateFormat = "01-02"
  # amount of RSS pages
  rss = 10
```

### Categories
Same with tags, category is another attribute for posts. 

## 5 Search {#search}
LoveIt support [Lunr.js](https://lunrjs.com/) and [algolia](https://www.algolia.com/) for searching. 

### algolia
**Algolia** is a cloud search service provider, we can put our data in JSON format on Algolia server, and search based on the API it provide. 
```toml
# Search config
[params.search]
  enable = true
  # type of search engine ["lunr", "algolia"]
  type = "algolia"
  # max index length of the chunked content
  contentLength = 4000
  # placeholder of the search bar
  placeholder = "java"
  # max number of results length
  maxResultLength = 10
  # snippet length of the result
  snippetLength = 30
  # HTML tag name of the highlight part in results
  highlightTag = "em"
  # whether to use the absolute URL based on the baseURL in search index
  absoluteURL = false
  [params.search.algolia]
    index = ""
    appID = ""
    searchKey = ""
```
Algolia lets user to upload 10,000 JSON data, and allow to do search 100,000/month for FREE. Don't wait to login to it and get the params we need in the application.

We need to synchronize the `public/index.json` to Algolia whenever we publish our site. 
The following config will let hugo generate `index.json` everytime we run `$ hugo`
```toml
# Output
[outputs]
  home = ["HTML", "RSS", "JSON"]
```
Upload this `index.json` to the index you created for specific application, 
{{<image src="/images/hugo_blog/algolia_1.png" caption="Create new index" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}
{{<image src="/images/hugo_blog/algolia_02.png" caption="Upload json file" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}

We also need to configure the searchable content of our content by changing Searchable attributes, 
{{<image src="/images/hugo_blog/algolia_03.png" caption="Create new index" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}


## 6 Comments
LoveIt support multiple comments API, including disqus, gitalk, valine, facebook comment, telegram comments, commento, utterance, giscus. 

If you store your souce code on Github, it's easy to use [utterances](https://utteranc.es/) via Github App. 
Just add this app into your repository.
{{<image src="/images/hugo_blog/utterance_01.png" caption="uterances app" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}

```toml
# Comment config
[params.page.comment]
  enable = true
  # utterances comment config
  [params.page.comment.utterances]
  enable = true
  # owner/repo
  repo = "LongYuu/LongYuu.github.io"
  issueTerm = "pathname"
  label = ""
  lightTheme = "github-light"
  darkTheme = "github-dark"
```
{{< admonition type="info" title="" open=true/false >}}
The comment widget only works on **production** environment, by default, the local environment is **development**.
{{< /admonition >}}

## 7 Deploy {#deploy}

### GitHub Pages
GitHub provides free and fast static hosting for project pages directly from Github repository, via its GitHub Pages service and automating development workflows and build with GitHub Actions.
We need to config the settings for GitHub repository to use GitHub Actions workflow for deployment, 

{{<image src="/images/hugo_blog/gitpage.png" caption="GitHub Actions for build and deployment" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}

A workflow config file `.github/workflows/hugo.yaml` is needed for GitHub Action,
```yaml
# Sample workflow for building and deploying a Hugo site to GitHub Pages
name: Deploy Hugo site to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches:
      - main

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

# Default to bash
defaults:
  run:
    shell: bash

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.114.0
    steps:
      - name: Install Hugo CLI
        run: |
          wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
          && sudo dpkg -i ${{ runner.temp }}/hugo.deb          
      - name: Install Dart Sass
        run: sudo snap install dart-sass
      - name: Checkout
        uses: actions/checkout@v3
        with:
          submodules: recursive
          fetch-depth: 0
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v3
      - name: Install Node.js dependencies
        run: "[[ -f package-lock.json || -f npm-shrinkwrap.json ]] && npm ci || true"
      - name: Build with Hugo
        env:
          # For maximum backward compatibility with Hugo modules
          HUGO_ENVIRONMENT: production
          HUGO_ENV: production
        run: |
          hugo \
            --gc \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"          
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v1
        with:
          path: ./public

  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v2
```

By the above setttings, if we push the repository it will trigger the build for the code and deploy on GitHub Pages. 
{{<image src="/images/hugo_blog/githubActions.png" caption="GitHub Actions for build and deployment" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}

Try to access the domain `<githubUsername>.github.io` to see your own Blog now!

