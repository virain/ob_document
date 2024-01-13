---
title: 域名配置
---
## 配置域名

1.  解析域名（国内服务器需做好备案）
2.  配置域名
	 修改需要配置HTTPS的应用目录内， 编辑`config` 文件中的`DOMAIN` 值为解析好的域名，然后在应用文件夹内运行 `docker compose up -d`，例如
	 ``` shell
	 cd /dockerapps/wordpress
	 sed -i 's/^DOMAIN*/DOMAIN=www.example.com/' config # 将 www.example.com 替换成自己的域名
	 docker compose up -d
	 ```



