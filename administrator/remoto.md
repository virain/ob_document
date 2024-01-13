---
title: 远程连接/文件传输
---
# 远程连接云服务器（通用）

准备好云服务器**管理员用户名**、**密码**、**公网IP**等信息，参考下面的内容连接到服务器
## 远程连接 Linux

Linux下我们推荐使用 **SSH/SFTP 工具去远程连接、管理和传输文件**。SSH 是一种可靠的、专为远程登录会话和其他网络服务提供安全性的协议,而 SFTP 是使用 SSH 协议的 FTP 模式，也称之为安全增强型的 FTP。

强烈推荐用户使用 WinSCP + PuTTY 的组合对 Linux 服务器进行远程管理和文件传输

### 配置 WinSCP

1. 下载 [WinSCP](https://winscp.net/) 和 [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/PuTTY/latest.html) 并安装。启动后，新建站点![](https://image.stacknil.com/images/WinSCP_T9IX2PQEq0.png)


> [!tip]
> PuTTY 建议下载 MSI 格式，安装过中保持默认设置


1. 设置登录密码/密钥，分别说明两种验证方式:
    - 密码登录![](https://image.stacknil.com/images/WinSCP_8aBFXK8aDE.png)

    - 秘钥登录![](https://image.stacknil.com/images/WinSCP_dp0GntWWrc.png)

2. 验证方式设置好之后，点击"登录"。登录中过程中，程序会提示您是否保存登录信息。

3. 成功连接后的界面 ![](https://image.stacknil.com/images/WinSCP_n0wOz0Kvsm.png)

### 管理/传输文件

WinSCP 通过拖拽，就可以方便上传下载文件，可以对文件（夹）可以对进行多种设置与操作 

![](https://image.stacknil.com/images/WinSCP_Rdb3jSxjJt.png)

1. 右键单击服务器上一个文件或文件夹，可以对云服务器进行多种操作

2. 以修改文件权限为例的相关界面如下![](https://image.stacknil.com/images/WinSCP_F6vbdmMdaj.png)
  
### 运行命令
WinSCP 拥有自带的命令控制台也可能集成使用 PuTTY 运行命令
#### 使用集成 PuTTY (推荐)

由于 WinSCP 自带命令控制台仅能够运行非交互式命令（即命令执行过程中无需反馈和过程中的输入），我们推荐将 PuTTY 集成到 WinSCP 上使用


> [! tip]
> 如果 PuTTY 是使用 MSI 格式安装的且安装过程保持默认设置，只需要在选项-集成-应用程序中勾选“记住会话密码并传给PuTTY”

1. 点开选项快捷图标-集成-应用程序，定位到本地 PuTTY 路径后保存即成功集成![](https://image.stacknil.com/images/WinSCP_HVLwMiFMRE.png)

2. 测试配置：通过 WinSCP 的窗口快捷方式打开 PuTTY![](https://image.stacknil.com/images/WinSCP_SQm916dJLO.png)
  
#### WinSCP 命令控制台
  
> [! note]
> WinSCP 命令控制台仅能执行非交互式命令（即命令执行过程中无需反馈和过程中的输入，如 `vim`,`top` 等交互式命令无法执行）


1. WinSCP登录到服务器，点击菜单来的命令窗口图标（快捷键 Ctrl+T）![](https://image.stacknil.com/images/WinSCP_FgkWmzQFgw.png)

2. 在弹出的命令控制台窗口后执行命令，以查询内存使用为例，运行命令 free -h ![](https://image.stacknil.com/images/WinSCP_EzmC4VXqNo.png)
## 远程连接 Windows

远程连接 Windows 服务器就相对简单很多了，可以通过本地电脑的远程桌面工具 (MSTSC) 进行连接

![](https://image.stacknil.com/images/mstsc_k2ZYyXmPsZ.png)

  
1. 打开本地电脑远程桌面的方式（三选一）:

    - 打开 开始菜单 -> 远程桌面连接

    - 打开 开始菜单，输入 “mstsc” ，系统会搜索远程桌面连接工具

    - 通过 Windows 键 + R 运行 mstsc 命令来启动远程桌面连接工具

  

2. 打开远程桌面连接，输入公网IP地址，通过更多选项，设置默认用户名（例如 “Administrator”），如需要保存用户名密码勾选“允许我保存凭据”,点击连接![](https://image.stacknil.com/images/WindowsSandboxClient_iIS3JjeRdp.png)

3. 连接成功后会看到Windows界面![](https://image.stacknil.com/images/WindowsSandboxClient_7KvWqywYee.png)

  

### 传输文件

  

#### 通过远程桌面连接（mstsc）

  
> [! warning]
> 不推荐用来传输大量文件和大容量文件

远程连接登录后，就可以直接从本地计算机上使用“复制”拷贝文件，然后在服务器上“粘贴”，将本地计算机的文件传输到服务器上。![](https://image.stacknil.com/images/WindowsSandboxClient_bLLEJwFEBx.png)