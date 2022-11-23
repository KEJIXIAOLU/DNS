# 科学上网：VPS 搭建 X-UI 面板，利用 DNS 申请证书

## 使用X-UI搭建代理服务，具有以下优点：

- 支持系统状态监控：如CPU、内存、硬盘等状态
- 支持多用户多协议，网页可视化操作
- 支持流量统计
- 支持自定义Xray配置模板
- 支持HTTPS访问面板
- 支持面板自定义端口，账号与密码
- 快速生成分享连接或二维码
- 支持CDN套用
- 支持Fallback分流设置

## 一、 准备工作

- 1、已经解析的域名，Win+R 输入CMD 回车：键入ping 空格输入你的域名，检查一下是否可以ping通
- 2、一台境外VPS主流系统，例如：Debian/Ubuntu/CentOS
- 3、下载并安装FinalShell SSH工具

Windows版下载地址:
http://www.hostbuf.com/downloads/finalshell_install.exe

macOS版下载地址:
http://www.hostbuf.com/downloads/finalshell_install.pkg

## 二、更新安装系统
下面环境的安装方式，大家根据自己的系统选择命令安装就好了。
### 1、Debian/Ubuntu系统执行以下命令：
    apt update -y         
    apt install -y curl    
    apt install -y socat    
    
### 2、CentOS系统执行以下命令：   

    yum update -y         
    yum install -y curl   
    yum install -y socat   

 ## 安装BBR加速
 本脚本建议在Debian≥9或是CentOS≥8以上的系统中使用
 
    wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh
 
 ## 一键安装面板
    bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
 
 完成 X-ui 安装以后，我们可以输入 VPSIP:端口（如1.1.1.1:12345） 登录 X-ui 的管理面板（可以登录代表安装成功）

## 利用 DNS 申请证书

在 VPS 输入<code> x-ui</code>  命令，进入 X-ui 的命令菜单
选择 16，申请 SSL 的证书。（申请需要有 Cloudflare API ，可以 观看视频 获取 API）
申请的时候是申请的泛域名证书，所以，填写域名的时候，只填入 域 也就好了，例如<code>  xxx.com</code>  的格式。

申请成功以后，证书和密钥文件在 VPS 目录的<code> /root/cert </code>文件夹里面

##  访问并设置 Xray 管理面板
在浏览器中输入刚才解析的域名 cs.kjxlu1.top ，用户名 admin ，密码 admin

修改必要的面板参数 SSL证书以及密钥（绝对地址）、面板端口、登录标题 等，其他若是你不清楚，请保持默认

-  重要：若是设置了 SSL证书以及密钥 ，再次登录需要输入 https://cs.kjxlu1.top:54321 访问，注意，是 https
 
 ## 添加科学上网节点
 请看视频演示
 
 
 
