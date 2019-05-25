+++
categories = ["tutorial"]
date = "2019-05-25T16:00:00+00:00"
tags = ["hugo"]
title = "Setting up a Hugo blog"

+++
Resources on how I setup my own blog with Hugo, Netlify, and Forestry. Log of problems I encountered and solutions I came across.

<!--more-->

Main tutorials I followed were:

* [Start a blog in 30 minutes with Hugo](https://opensource.com/article/18/3/start-blog-30-minutes-hugo)
* [Hugo101](https://medium.com/backticks-tildes/hugo101-getting-started-with-hugo-and-deploying-to-netlify-9a813fe23b94)
* [Hugo docs on Netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/)
* [Netlify guide on Hugo](https://www.netlify.com/blog/2016/09/21/a-step-by-step-guide-victor-hugo-on-netlify/#setting-up-your-first-theme)
* [Build your own blog with Hugo and Netlify](https://dev.to/effingkay/build-your-own-blog-with-hugo-and-netlify-oi7)


## Netlify deployment issue with Cactus Plus theme
Netlify kept throwing out a `Error: Unable to find theme Directory: /themes/XXX` error. It has something to do with submodules and the `.git` sub-directory. More info can be read [here](https://discourse.gohugo.io/t/netlify-site-does-not-deploy/12001/17).
The tldr; solution is to just manually install the theme via downloading the zip file, renaming extracted folder, and moving folder to `themes/` directory. 

The only con is that the theme no longer updates automatically. In this case it isn't as big a loss since Cactus Plus was last updated in 2018.