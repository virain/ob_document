---
title: 配置 HTTPS/SSL
---
## 使用 Let's Encrypt 免费证书

[[domain|配置域名]]后,系统将自动为你生成并配置 Let's Encrypt 免费证书

## 自有证书
1. 上传自有证书到服务器
2. 导入自有证书
	1.  进入 traefik 目录
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

3. 证书导入后,[[domain|配置域名]],系统会自动识别分配证书