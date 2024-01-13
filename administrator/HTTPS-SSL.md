---
title: 配置 HTTPS/SSL
---
# HTTPS

https(全称：Hyper Text Transfer Protocol over Secure Socket Layer)，是以安全为目标的http通道，简单讲是http的安全版。

https相当于在HTTP下加入SSL层，https的安全基础是SSL，因此加密的详细内容就需要SSL。 它是一个URI scheme(抽象标识符体系)，句法类同http:体系。用于安全的HTTP数据传输。

https也叫安全的超文本传输协议，使用TCP端口443，他的数据会用PKI中的公钥进行加密，这样抓包工具捕获到的数据包也没有办法看包中的内容，安全性大大提高，要解密数据的话就要用到PKI中的私钥。所以一些安全性比较高的网站如：网上银行，电子商务网站都需要用https访问。
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