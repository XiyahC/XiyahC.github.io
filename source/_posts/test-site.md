---
title: Develop Doc
date: 2022-09-27 15:39:01
tags:
# top_img: https://e-imagedata.com/assets/data/images/febblog3.jpg
cover: https://e-imagedata.com/assets/data/images/febblog3.jpg
---

Sidenote on webpage update:  
hexo g == hexo generate #生成  
hexo s == hexo server #启动服务预览  
hexo d == hexo deploy #部署  

Sidenote on macbook update:  
hexo g  
hexo s  
hexo clean  
hexo d -g  

then will see master branch updated  

git pull  
git add -A  
git commit -m "comments"  
git push origin hexo  

Those above allows updating new things to hexo branch.  

Before each time start writing, remeber first do  

git pull  

to see any update.  

* ssh changed 2025


网页跳转：  

    [站内跳转]{% post_path blog/hexo-01-框架篇 %}：站内跳转.  
    [页内跳转](#music)：页内跳转. 只有一级标题可以跳转。  
Useful link: https://github.com/iissnan/hexo-theme-next/issues/978
