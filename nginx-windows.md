# windows install nginx
* 下载地址 https://nginx.org/en/download.html 
* 解压到硬盘
* 启动脚本

```cmd
cd ../nginx1.22.1
start nginx
```
 * 停止脚本

```cmd
cd ../nginx1.22.1
nginx -s stop
```

 * nginx.conf 配置文件

```conf
server {
	   listen       80;
	   server_name  域名/外网IP;

	   location / {
	      root   /home/wwwroot/eladmin/dist;
	      index  index.html;
	   }
}

```