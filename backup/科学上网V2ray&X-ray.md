### 支持多协议多用户的 xray 面板

适配Alpine linux 使用F大编译的x-ui，支持的协议：vmess、vless、trojan、shadowsocks、dokodemo-door、socks、http
默认端口可使用x-ui命令更换
ovz，lxc虚拟化的vps，在纯净系统首次安装后内存占用约为27m左右，重启后内存占用约为20m

### 功能介绍
| Header | Header | Header |
|--------|--------|--------|
| 系统状态监控 | 支持配置更多传输配置 | 可自定义 xray 配置模板 |
| 支持多用户多协议，网页可视化操作 | 支持 https 访问面板（自备域名 + ssl 证书） | 更多高级配置项，详见面板 |
| 流量统计，限制流量，限制到期时间 | 支持一键SSL证书申请且自动续| ヾ(•ω•`)o |

### 安装工具
```
1、[安装finalshell](https://www.hostbuf.com/t/988.html)
2、安装X-UI面板
3、[安装v2ray](https://github.com/2dust/v2rayN/releases)
```
### 使用代码
1、开启防火墙
```
iptables -P INPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -P OUTPUT ACCEPT
iptables -F
apt-get purge netfilter-persistent
输入reboot，重启服务器
```
2、申请SSL证书
```
apt update -y       # Debian/Ubuntu 命令
apt install -y curl   # Debian/Ubuntu 命令
apt install -y socat  # Debian/Ubuntu 命令

yum update -y        #CentOS 命令
yum install -y curl    #CentOS 命令
yum install -y socat   #CentOS 命令

curl https://get.acme.sh | sh

~/.acme.sh/acme.sh --register-account -m example@xx.com（替换成自己的邮箱）
```
3、开始申请证书
```
~/.acme.sh/acme.sh --issue -d 域名 --standalone   
#替换成自己解析好的域名，注意前后要有空格
```
4、安装证书
```
~/.acme.sh/acme.sh --installcert -d 域名 --key-file /root/private.key --fullchain-file /root/cert.crt    
#部分替换成自己解析好的域名，注意前后要有空格
#刷新Fianlshell窗口，在root目录下可看到证书公钥/root/cert.crt及验证文件/root/private.ke
```
5、安装X-UI面板
```
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```

6、如果打不开v2rayN.exe,可以安装[.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)，下载链接：https://docs.microsoft.com/zh-cn/dotnet/framework/install/guide-for-developers

<p align="center">
❤️ 转载文章请注明出处，谢谢！❤️
</a></p>












