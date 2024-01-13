---
title: 域名配置
---
# 域名
在 Internet 上有千百万台主机，为了区分这些主机，每一台主机都被分配一个 IP 地址。但由于 IP 地址没有实际意义且难于记忆，于是就有了域名（Domain Name）。

域名主要是由英文字母、阿拉伯数字、“ - ” 、“ . ” 等组成，目的是为了方便记忆和沟通一组服务器的地址（网站、电子邮件、FTP 等）。

域名和 IP 是相互对应的，在 Internet 上专门有 DNS（域名服务器）来进行域名与 IP 的相互转换，您在浏览器上输入域名， DNS 会进行域名与 IP 的转换，才能找到相应的服务器，打开相应的网页。

如果您想要在 Internet 上建立服务器发布信息，则要先注册相应的域名。域名注册是在 Internet 上建立服务的基础，由于域名的注册以 “先申请先注册” 为原则，在互联网中每一个域名的注册都是不可重复的，如果您想在 Internet 上拥有您的服务器发布信息，建议尽早注册域名。
## 新注册域名

如果您想通过一个域名来提供您的网站、邮箱等业务服务，您可以在域名注册平台上注册一个属于您的域名。注册域名后，您还需完成**实名认证**、**备案**、**解析流程**，最终您的域名可被访问并对外提供服务。

![](https://image.stacknil.com/images/msedge_x16dqNYOQV.png)

  
详细内容请参考下表：

| 域名注册平台 | 说明 |
| ------------ | ---- |
| [阿里云域名注册](https://wanwang.aliyun.com/) | [注意事项](https://help.aliyun.com/document_detail/61257.html) |
| [腾讯云域名注册](https://dnspod.cloud.tencent.com/) | [注意事项](https://cloud.tencent.com/document/product/242/39039) |
## 配置域名

1.  解析域名（国内服务器需做好备案）
2.  配置域名
	 到需要配置HTTPS的应用路径下， 编辑`config` 文件中的`DOMAIN` 值为解析好的域名，然后在应用文件夹内运行 `docker compose up -d`，例如
	 ``` shell
	 cd /dockerapps/wordpress
	 sed -i 's/^DOMAIN*/DOMAIN=www.example.com/' config # 将 www.example.com 替换成自己的域名
	 docker compose up -d
	 ```



