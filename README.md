## 博客网址

https://xiyahc.github.io/

## 一些常见问题备忘

1. 从vscode push 到Github之后，README.md被删除，需要在```_config.yml```中修改```skip_render:README.md```.  

2. 网站页面重新部署后经常没办法同步更新，需要```ctrl+F5```强制刷新.  

3. Algolia Search.  
   当报错'ERROR [hexo-algolia] Please set an `HEXO_ALGOLIA_INDEXING_KEY` environment variable to enable content indexing.'.  
     需要临时在git bash中执行'export HEXO_ALGOLIA_INDEXING_KEY=你的Admin API Key'，重启失效.  
     报错解决网站：http://werty.cn/2019/07/hexo/hexo%20algolia%E5%91%BD%E4%BB%A4%E6%89%A7%E8%A1%8C%E5%A4%B1%E8%B4%A5%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88/ .  

4. Valine评论系统： https://blog.csdn.net/qq_35117024/article/details/107248047.  

5. Valine EmojiCDN: 

   ​	- https://valine.js.org/en/cdn.html .  

    - https://valine.js.org/emoji.html （自定义）
    - [(2条消息) valine自定义表情正确打开方式_Honmaple的博客-CSDN博客](https://blog.csdn.net/Honmaple/article/details/106051639)

6. PWA安装：（网页PWA的问题目前未解决）

   ​	- [hexo 博客开启 pwa | GYH's Blog (imgyh.com)](https://www.imgyh.com/posts/805d5d89/#post-comment)

   ​	- hexo-offline：[JLHwung/hexo-offline: Out-of-the-box hexo offline experience (github.com)](https://github.com/JLHwung/hexo-offline)

7. 检查hexo和node.js更新

   ​	- [将 Hexo 升级到 v4.2.1 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/157511323)

8. hexo-douban插件

   ​	因为这个插件刚装好之后,```hexo douban```爬不到豆瓣数据, 上网查过之后需要将node和npm版本降到```v12.18.0```. 由于我最开始下载nodejs和npm并没有用nvm, 所以直接手动uninstall＋install导致我这个小白不知道解完压之后文件都跑去了哪里. 在重新刷机之后, 用nvm下载了最新版本的nodejs和v12.18.0版本的nodejs. Default设定为v12.18.0. 这时再去运行```hexo-douban```就可以爬到数据了.

9. 音乐的使用

   ​	[hexo-tag-aplayer/README-zh_cn.md at master · MoePlayer/hexo-tag-aplayer (github.com)](https://github.com/MoePlayer/hexo-tag-aplayer/blob/master/docs/README-zh_cn.md)

   ​	[Butterfly添加全局吸底Aplayer教程 | Butterfly](https://butterfly.js.org/posts/507c070f/#插入Aplayer-html)

   ​	[给Hexo添加音乐播放器插件 | Freemon (ftzzloo.com)](https://ftzzloo.com/hexo-add-aplayer-plugins/)

10. 友情链接加在侧边栏的实现

    ​	[Hexo-theme-butterfly修改调整记录教程 | LarsCheng](https://www.larscheng.com/butterfly/#其他小改动)

11. 小细节调整

    ​	[Hexo Butterfly 主題：我的自定義配置及修改 | 我的倉庫 | ouoholly](https://ouoholly.github.io/post/my-custom-config-on-hexo-butterfly-theme/#Tags：移至文章上方)

12. sdf

## Butterfly主题教程

https://butterfly.js.org/archives/page/2/




