> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.yundashi168.com](https://www.yundashi168.com/174.html)

> 官网又给这个系统进行了加强版：~wookteam~ github 站点仓库已删除 支持在线即时聊天等功能，非常强 […]

> 官网又给这个系统进行了加强版：[~wookteam~](https://github.com/kuaifan/wookteam) github 站点仓库已删除  
> 支持在线即时聊天等功能，非常强大。值得去体验和使用。  
> 源码：https://gitee.com/aipaw/wookteam  
> 官网：https://www.wookteam.com

kooteam 官网：[https://www.kooteam.com/](https://www.kooteam.com/ "https://www.kooteam.com/")

kooteam 是一款轻量级的在线团队协作工具，提供各类文档工具、在线思维导图、在线流程图、项目管理、任务分发，知识库管理等工具。  
kooteam 支持钉钉，企业微信等账号同步登陆，保障企业数据安全。

[![](https://i.loli.net/2021/01/05/m7lKwNV3dGeoTxb.jpg)](https://i.loli.net/2021/01/05/m7lKwNV3dGeoTxb.jpg)

主要功能
----

*   待办四象限：突出事情优先级，帮助员工合理安排时间，提高工作效率。
*   项目管理：自定义项目看板，可视化任务安排。
*   在线知识库：在线流程图，在线文档，以及可视化的目录编排，文档管理无忧。
*   日程管理：可视化日程管理，快速搞定工作计划，了解工作宏观安排
*   在线流程图：在线流程图工具，使用方便
*   在线思维导图：梳理思路，优化工作流程

Kooteam 作为一个免费开源的团队在线协作工具，没有那么多花里胡哨，要的都是实用的功能，且支持私有化部署，安全有保障。还是比较适合中小微企业应用的。

**项目下载地址** [https://gitee.com/sinbo/kooteam](https://gitee.com/sinbo/kooteam)

> 官网部署教程：[https://www.kooteam.com/view.html?id=5e5893bdc687557cc87e38c5](https://www.kooteam.com/view.html?id=5e5893bdc687557cc87e38c5)

前提条件
----

*   条件 1：java 运行环境：jdk 8
*   条件 2：数据库：MySql 5.6 以上版本 (包含了 5.6 版本)
*   条件 3：域名 1 个，这里用的是[阿里云域名](https://www.aliyun.com/?source=5176.11533457&userCode=ywqc0ubl&type=copy "阿里云域名")
*   条件 4：云服务器一台 (尽量选 linux 系统)，用的是[阿里云服务器](https://begin.yundashi168.com/aliyun/index "阿里云服务器")
*   条件 5：云服务器上安装宝塔面板

【强烈建议使用 Linux 服务器安装】，windows 环境需要安装 cmder  
windows 服务器：安装 cmder 工具，再通过 cmder 执行下面命令和运行 shell 脚本

条件 1 可以参考教程：[Linux 安装 jdk8 以及配置环境变量](https://www.yundashi168.com/172.html)  
条件 2 安装 MySql5.6 可以选择自己在 Linux 系统手动安装，也可以选择用宝塔面板来一键安装。  
由于想简单点，主要是想节省时间和精力，我就在宝塔面板上安装好了 LNMP 架构环境，其中的 mysql 选 5.6 以上版本。  
不知道在 Linux 服务器上安装和使用宝塔面板的可以参考我写的经典教程：[基于阿里云 Linux 服务器搭建宝塔面板完整图文教程](http://tencent.yundashi168.com/327.html)

正式安装
----

1.  curl -L -o kooteam.tar.gz ‘[https://www.kooteam.com/home/download.do?app=kooteam&type=install&#8217](https://www.kooteam.com/home/download.do?app=kooteam&type=install&#8217);  
    注意事项：一定要先切换到你的目标目录之后，再执行上面的命令。上面的命令是下载 kooteam.tar.gz 这个压缩文件的。

> 温馨说明：官网已经不提供 kooteam.tar.gz 下载. 所以这里我给出云盘下载地址  
> [http://share.vpssw.com/f/28426853-496964201-3a48ce](http://share.vpssw.com/f/28426853-496964201-3a48ce)  
> （访问密码：7569）

2.  tar -xvf kooteam.tar.gz
3.  执行 sh ./start.sh 脚本启动服务
    
4.  宝塔面板提前创建好一个 mysql 数据库。
    
5.  浏览器中访问 kooteam，输入地址: [http:// 服务器 IP:7053/](http://xn--ip-fr5c86lx7z:7053/)  
    出现如下界面：  
    [![](https://i.loli.net/2021/01/05/3ypexlVdZA2OcSH.jpg)](https://i.loli.net/2021/01/05/3ypexlVdZA2OcSH.jpg)  
    输入数据库账号信息，校验通过后保存，即完成系统安装。这一步很简单。不多说了。
    
6.  处理二级域名与端口转发问题。  
    正常的，我们都不希望通过 “域名”+“端口号” 的方式给别人用吧。常见的做法就是用二级域名 + Nginx 处理下端口转发问题。  
    没处理之前，我们是这样访问： [https://tast.vpssw.com:7053/](https://tast.vpssw.com:7053/)  
    处理之后，我们可以这样访问： [https://tast.vpssw.com](https://tast.vpssw.com/)
    
    **Nginx 配置：**
    

```
server
{
    listen 80;
    listen 443 ssl http2;
    server_name task.vpssw.com;
    index index.php index.html index.htm default.php default.htm default.html;
    root /www/wwwroot/task.vpssw.com/res;

    location / { 
      proxy_set_header X-Real-IP $remote_addr;
      proxy_set_header Host  $http_host;
      proxy_pass http://127.0.0.1:7053;
    }

    ssl_certificate    /www/server/panel/vhost/cert/task.vpssw.com/fullchain.pem;
    ssl_certificate_key    /www/server/panel/vhost/cert/task.vpssw.com/privkey.pem;
    ssl_protocols TLSv1.1 TLSv1.2 TLSv1.3;
    ssl_ciphers EECDH+CHACHA20:EECDH+CHACHA20-draft:EECDH+AES128:RSA+AES128:EECDH+AES256:RSA+AES256:EECDH+3DES:RSA+3DES:!MD5;
    ssl_prefer_server_ciphers on;
    ssl_session_cache shared:SSL:10m;
    ssl_session_timeout 10m;
    add_header Strict-Transport-Security "max-age=31536000";
    error_page 497  https://$host$request_uri;
    include enable-php-74.conf;
    include /www/server/panel/vhost/rewrite/task.vpssw.com.conf;
    location ~ ^/(\.user.ini|\.htaccess|\.git|\.svn|\.project|LICENSE|README.md)
    {
        return 404;
    }
    location ~ \.well-known{
        allow all;
    }
    location ~ .*\.(gif|jpg|jpeg|png|bmp|swf)$
    {
        expires      30d;
        error_log /dev/null;
        proxy_pass http://127.0.0.1:7053;
        access_log off;
    }
    location ~ .*\.(js|css)?$
    {
        expires      12h;
        error_log /dev/null;
        proxy_pass http://127.0.0.1:7053;
        access_log off; 
    }
    access_log  /www/wwwlogs/task.vpssw.com.log;
    error_log  /www/wwwlogs/task.vpssw.com.error.log;
}


```

7.  为系统设置 ssl 安全证书。  
    这一步，我以前写过详细教程，学习可以参考教程[宝塔面板设置 ssl 安全证书完整图文教程](http://tencent.yundashi168.com/652.html)
    
8.  系统完美部署成功。
    

系统命令
----

```
1. ./start.sh 启动应用
2. ./start.sh upgrade 升级应用
3. ./start.sh stop 关闭应用
4. ./start.sh restart 重启应用


```

原文地址：[猿视野](https://www.yundashi168.com/174.html)
