---
title: Hexo配置
date: 2019-01-13 10:43:09
tags: hexo
---

## 前言
試著嘗試了一下hexo+github來用markdown寫blog，試用了一下就決定放棄logdown。簡單記錄一下我怎麼設置hexo，將blog部屬在github上。

## Prerequisite
* 安裝 Node.js
* 安裝 git
* [GitHub Pages](https://pages.github.com/)


## Installation

### 安裝Hexo
``` bash
$ npm install hexo-cli -g
$ hexo init blog
$ cd blog
$ blog> npm install
```

### 安裝git plug-in

``` bash
$ blog> npm install hexo-deployer-git --save
```

## 設定 blog/_config.yml

``` yml
# Site
title: # blog標題
subtitle: # 副標題
description:
author: # 作者名稱
language: zh
timezone: Asia/Taipei

# Writing
new_post_name: :year-:month-:day-:title.md 
# 官方建議設置，方便管理檔案

# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/{帳號名稱}/{帳號名稱}.github.io.git
  branch: master
#注意階層關係
```

## 更改blog主題(themes)

主題放在 blog/themes/，預設為landscape。[下載themes](https://hexo.io/themes/)，需要更改blog/_config.yml

``` yml
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: landscape # 更改成下載的主題名稱
```

## 編輯與發佈

### 啟動
```bash
$ blog> hexo clean
$ blog> hexo g
$ blog> hexo s
```

### 預覽
> localhost:4000

### 發布

```bash
$ blog > hexo d
```

## 備份blog設定和文章

### 利用github備份

* scaffolds/
* source/_posts
* themes/
* .gitignore
* _config.yml
* package.json

### 範例
https://github.com/jockey66666/blog


## 編輯工具

* vscode
  * Markdown All in One
  * GitLens