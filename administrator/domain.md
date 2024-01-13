---
title: 域名配置
---
# 关于域名

在Internet上有千百万台主机，每一台主机都被分配一个IP地址以区分。但由于IP地址没有实际意义且难于记忆，因此出现了域名（Domain Name）。

域名主要由英文字母、阿拉伯数字、"-"、"."等组成，其目的是为了方便记忆和沟通一组服务器的地址（如网站、电子邮件、FTP等）。

域名与IP地址是相互对应的。在Internet上，有专门的DNS（域名服务器）用于域名与IP的相互转换。当您在浏览器中输入域名时，DNS会进行域名与IP的转换，从而找到相应的服务器，打开对应的网页。

如果您想在Internet上建立服务器发布信息，您需要先注册相应的域名。域名注册是在Internet上建立服务的基础。由于域名的注册是按照“先申请先注册”的原则进行的，每个域名在互联网中都是不可重复的。因此，如果您计划在Internet上拥有您的服务器并发布信息，建议尽早注册域名。

## 新注册域名

如果您希望通过一个域名提供您的网站、邮箱等业务服务，您可以在域名注册平台上注册一个属于您的域名。注册域名后，您还需要完成**实名认证**、**备案**和**解析流程**，最终您的域名将能够被访问并对外提供服务。

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



