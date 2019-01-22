---
title: 為Hexo新增留言區
date: 2019-01-13 14:55:24
tags: hexo
categories: [github, hexo]
---

## 目的
為了新增評論區，申請了[disqus](https://disqus.com/)

## 步驟
1. Add Disqus To Site
2. 設定 Website Name
3. 複製Universal Code到themes/{theme_name}/layout/post.ejs
4. 重新佈署 hexo

## 2019/1/22

我發現我的themes/clean-blog/_config.yml裡面可以直接填入disqus的short name，省去每次切換文章時disqus讀進來的時間。