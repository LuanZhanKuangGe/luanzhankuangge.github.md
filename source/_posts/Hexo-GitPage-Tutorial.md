---
title: Git Page + Hexo 博客搭建
date: 2019-02-01 11:03:18
categories: 趣味教程
tags: 
- Web 
- NodeJS
---
___

## 本地部署Hexo

1. 安装nodeJS.
2. 安装Git.
3. 执行npm install -g hexo
4. 执行npm install hexo-deployer-git --save
5. 新建$HOME_PAGE目录，执行hexo init
6. 执行hexo server，访问[localhost](http://localhost:4000/)测试

___

## GitPage部署

1. 修改配置文件_config.yml，需重启server生效.

    ```
    #Site
    title: 程序员之乱  
    subtitle: 程序员那些乱七八糟的事ʅ(‾◡◝)ʃ  
    description: 程序员那些乱七八糟的事ʅ(‾◡◝)ʃ  
    author: 乱战狂歌  
    language: zh  
    timezone: Asia/Shanghai
    ```

2. 在GitHub上新建仓库$YOUR_GIT_NAME.github.io. 在仓库Settings中打开GitHub Pages.

3. 并配置_config.yml.

    ```
    # URL
    url: https:/$YOUR_GIT_NAME.github.io/
    root:
    permalink: :year/:month/:day/:title/
    permalink_defaults:

    # Deployment
    deploy:
    type: git
    repository: https://github.com/$YOUR_GIT_NAME/$YOUR_GIT_NAMEE.github.io.git
    branch: master
    ```

4. 运行hexo deploy部署文件.

___

## 常用Hexo操作

* 本地运行hexo服务器：hexo server
* 新建md文章：hexo new “your_post”
* 生成静态网页文件：hexo generate
* 部署文件：hexo deploy
* 清理生成文件：hexo clean

___

## 图片上传功能
1. 执行npm install hexo-asset-image --save
2. 修改_config.yml中post_asset_folder为true.
3. 再次执行hexo new “your_post”会同时生成your_post文件夹，使用该相对路径插入图片即可

___
## note

* Hexo使用[GFM](https://help.github.com/categories/writing-on-github/), 和标准Markdown略有不同：
* 部署文件不生效, 运行hexo clean试试.
* 新手主题推荐next，官方文档很详细.