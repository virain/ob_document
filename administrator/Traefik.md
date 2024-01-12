---
title: 反向代理
---

## 简介
**Traefik** 是一款用于反向代理和负载均衡的开源工具，特别适用于容器化应用。它能自动发现和管理容器服务，支持多种后端系统，提供简单配置和自动SSL功能，使得在现代应用架构中轻松实现动态路由和负载均衡。
![](https://img.stacknil.com//20240112225857.png)

## 管理/配置指南

Traefik 做为反向代理工具，已在镜像中做好基本配置，开箱即用

### 配置域名

>[! tip]  
>配置域名后 Traefik 将自动为你申请免费证书并配置


1.  解析域名（国内服务器需做好备案）
2.  配置域名
	 修改需要配置HTTPS的应用目录内， 编辑`config` 文件中的`DOMAIN` 值为解析好的域名，然后在应用文件夹内运行 `docker compose up -d`，例如
	 ``` shell
	 cd /dockerapps/wordpress
	 sed -i 's/^DOMAIN*/DOMAIN=www.example.com/' config # 将 www.example.com 替换成自己的域名
	 docker compose up -d
	 ```

### 配置 HTTPS/SSL

#### 使用 Let's Encrypt 免费证书

 Traefik 默认配置全局 SSL，只需要[[#配置域名]],系统将自动为你配置

#### 自有证书
1. 上传自有证书到服务器
2. 导入自有证书
	1.  进入 Traefik 目录
		 ``` shell
		 cd /dockerapps/traefik
         ```
    2.  修改动态配置
	    ``` shell
	    vim config/dynamic.yaml
		```
	3.  参考下面模板，修改自有证书路径
		 ``` yaml
		 tls:
		   certificates:
		     - certFile: /ssl/www.example1.com.pem
			   keyFile: /ssl/www.example1.com.key
		     - certFile: /ssl/www.example2.com.pem
			   keyFile: /ssl/www.example2.com.key
		 ```

3. 证书导入后,[[#配置域名]]系统会自动识别分配证书


