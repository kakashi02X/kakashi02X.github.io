---
layout: post
title: Why Jekyll and How to set it up ?
date: 2024-06-30 22:28
category: jekyll
author: kakashi
tags: [jekyll,blog]
summary: Intro to setting up jekyll.
---

Hello World,

Back to Blogging after years, and one of the reason is Jekyll. So What makes it so special ? 
Unlike the conventional wordpress or Social Media posts, This post is fired up using git commit, developed / previewed via a docker container and the satisfaction of setting up this chain and seeing it go live gives that extra ounce of happiness. Posts here are mostly a reminder to myself due to my short term memory like 'Memento'.

###  Set it Up !
- Fork the Theme : This website uses chirpy Starter, repository Name should match the username.github.io
- Configure Pages and Deploy Mode: From Repository Settings, Update the configuration for Build and Deployment for the Pages tab. Use Github Actions and choose Jekyll Configure option.
- Set the Local Dev using Docker : 
    - ```yaml            
        services:
        jekyll:
            image: bretfisher/jekyll-serve
            volumes:
            - .:/site
            ports:
            - '4000:4000'
            command: bundle exec jekyll s --force_polling -H 0.0.0.0 -P 4000 --livereload         
         ```
- Visual Studio Plugin : [Useful for Creating Posts](https://marketplace.visualstudio.com/items?itemName=rohgarg.jekyll-post)
- Use CDN for managing images & Static Content, CDN can be setup via [JSDeliver](https://www.jsdelivr.com/) which supports github repository.

That sums up my first Post !