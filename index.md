## 工作办公

. [蓝湖](https://lanhuapp.com/web/#/item?cid=&fid=all&commonly=join)

. [腾讯文档](https://docs.qq.com/desktop/)

. [szyj gitlab](http://120.24.100.216/)

. [szyj jenkins](http://192.168.1.249:18080/)

. [南方医EyeBlue](http://120.24.100.216:8810/?page=0&pageSize=50&orderCreateTime=DESC&puuid=30d03581-8506-42f9-6232-1fc72302868c&userUuid=89cf7ffd-d348-4164-64e2-f0a00bdbfdde&orderDir=DESC)

. [nginx 8001](http://localhost:8001)

## 卒中中心

. [卒中前端接口文档](http://120.24.100.216/weidongnian/szyj.stroke/blob/develop/%E5%89%8D%E7%AB%AF%E6%8E%A5%E5%8F%A3%E5%9C%B0%E5%9D%80.md)

. [卒中本地接口](http://localhost:62999/swagger/index.html)

. [卒中内网接口](http://192.168.1.249:62999/swagger/index.html)

. [卒中认证接口](http://192.168.1.249:64999)

. [卒中内网pc](http://192.168.1.249:8001/platform.html#/login)

. [卒中后台](http://192.168.1.249:63998/)


## 胸痛中心

. [胸痛前端接口文档](http://120.24.100.216/weidongnian/szyj.stroke/blob/chestPainCenter/%E5%89%8D%E7%AB%AF%E6%8E%A5%E5%8F%A3%E5%9C%B0%E5%9D%80.md)

. [胸痛内网接口](http://192.168.1.249:52999)

. [胸痛本地接口](http://localhost:52999)

. [胸痛内网pc](http://192.168.1.249:8001/chest/chest.html)

. [胸痛后台](http://192.168.1.249:63998/)


## 前端

. [vue](https://cn.vuejs.org/v2/guide/)

. [elementUI](https://element.eleme.cn/#/zh-CN/component/)

. [vuex](https://vuex.vuejs.org/zh/guide/)

. [jq datatables](http://datatables.club/reference/)

## 收藏

1. [abp vnext](https://docs.abp.io/zh-Hans/abp/latest/)

2. [asp.net core](https://docs.microsoft.com/zh-cn/aspnet/core/)

3. [bing.com](https://cn.bing.com/)

4. [dotnet core优秀的库、框架、项目](https://github.com/jasonhua95/awesome-dotnet-core/blob/master/README_CN.md)

5. [Jenkins](https://jenkins-zh.cn/wechat/)

6. [vue表单生成器](https://mrhj.gitee.io/form-generator/#/)

## 博客

* [abp vnext api host 项目中未启用Oauth2认证，需要手动开启](./page/blogs/abpVnextSwaggerIdentity4.md)

* [abp vnext 加上后台作业监听RabbitMQ事件发来的消息事件](./page/blogs/abp_vnex_backgroundWorkers_subscribe.md)

* vue router 多级路由加上默认子页跳转

* One or more errors occurred. (A DbContext can only be created inside a unit of work!)

    手动开启unitOfWork,使用AsyncHelp

* jenkins + docker 运行abp vnext 框架出现的一些问题和解决方法
  
  1. 因为 docker 默认无法访问外部网站，所以build 时要加上 --network=host 
    
        docker build -t 影像名称 -f 目录/Dockerfile . --network=host

  2. 因为 docker build 失败导致许多无用images占用时大量空间，要消除
  
        docker ps -a | grep "Exited" | awk '{print $1 }'|xargs docker stop
        
        docker ps -a | grep "Exited" | awk '{print $1 }'|xargs docker rm
        
        docker images|grep none|awk '{print $3 }'|xargs docker rmi
    
    
## 格言

* [业精于勤荒于嬉，行成于思毁于随](https://github.com/weidongnian/weidongnian.github.io/blob/master/index.md)
