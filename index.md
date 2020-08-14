## 工作办公

. [蓝湖](https://lanhuapp.com/web/#/item?cid=&fid=all&commonly=join)

. [腾讯文档](https://docs.qq.com/desktop/)

. [szyj gitlab](http://120.24.100.216/)

. [szyj jenkins](http://192.168.1.249:18080/)

. [南方医EyeBlue](http://120.24.100.216:8810)

. [南方医院内EyeBlue](http://10.10.252.168:6010/user)

. [nginx 8001](http://localhost:8001)

. [内网数据库工具](http://192.168.0.74:8082/)

## 卒中中心

. [卒中前端接口文档](http://120.24.100.216/weidongnian/szyj.stroke/blob/develop/%E5%89%8D%E7%AB%AF%E6%8E%A5%E5%8F%A3%E5%9C%B0%E5%9D%80.md)

. [卒中本地接口](http://localhost:62999/swagger/index.html)

. [卒中内网接口](http://192.168.1.162:30001/swagger/index.html?urls.primaryName=%E5%8D%92%E4%B8%AD%E4%B8%AD%E5%BF%83%E6%9C%8D%E5%8A%A1)

. [卒中认证接口](http://192.168.1.162:30001/api/oauth)

. [卒中内网pc](http://192.168.1.162:30001/stroke-web/stroke/stroke.html)

. [卒中后台74](http://192.168.0.74:63998/)

. [卒中后台162](http://192.168.1.162:30003/)

. [卒中外网pc](http://120.24.100.216:30001/stroke-web/stroke/stroke.html#/patients/index)


## 胸痛中心

. [胸痛前端接口文档](http://120.24.100.216/weidongnian/szyj.stroke/blob/chestPainCenter/%E5%89%8D%E7%AB%AF%E6%8E%A5%E5%8F%A3%E5%9C%B0%E5%9D%80.md)

. [胸痛内网接口](http://192.168.1.162:30001/swagger/index.html?urls.primaryName=%E8%83%B8%E7%97%9B%E4%B8%AD%E5%BF%83%E6%9C%8D%E5%8A%A1)

. [胸痛本地接口](http://localhost:52999)

. [胸痛内网pc](http://192.168.1.162:30001/stroke-web/chest/chest.html)

. [胸痛后台](http://192.168.0.79:63998/)

## 手术麻醉

. [手麻Api接口](http://192.168.1.162:30018/swagger/index.html)


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
        
  3. kubectl 创建 configmap
   
        kubectl create cm api-server-config --from-file=ocelot.json=./ocelot.json --from-file=appsettings.json=./appsettings.json  --dry-run -o yaml
    
## 格言

* [业精于勤荒于嬉，行成于思毁于随](https://github.com/weidongnian/weidongnian.github.io/blob/master/index.md)
