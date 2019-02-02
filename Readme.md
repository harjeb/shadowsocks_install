![Shadowsocks](https://github.com/teddysun/shadowsocks_install/raw/master/shadowsocks.png)
# Auto install Shadowsocks Server

shadowsocks.sh
===============
- Auto Install Shadowsocks(Python) Server for CentOS/Debian/Ubuntu
- https://teddysun.com/342.html

shadowsocks-libev.sh
===============
- Auto Install Shadowsocks(libev) Server for CentOS
- https://teddysun.com/357.html

shadowsocks-libev-debian.sh
===============
- Auto Install Shadowsocks(libev) Server for Debian/Ubuntu
- https://teddysun.com/358.html

shadowsocks-go.sh
===============
- Auto Install Shadowsocks(Go) Server for CentOS/Debian/Ubuntu
- https://teddysun.com/392.html

shadowsocks-crond.sh
===============
- Check Shadowsocks(All version) Server is running or not, and start it if not running
- https://teddysun.com/525.html

shadowsocksR.sh
===============
- Auto Install ShadowsocksR Server for CentOS/Debian/Ubuntu
- https://shadowsocks.be/9.html

shadowsocks-all.sh
==================
- Auto Install Shadowsocks Server (all version) for CentOS/Debian/Ubuntu
- https://teddysun.com/486.html

haproxy.sh
===============
- Auto Install haproxy for Shadowsocks Server
- https://shadowsocks.be/10.html

Copyright (C) 2014-2019 Teddysun




已获得 https://teddysun.com/486.html 的缓存页面
下面是网页在 2019/2/1 时(我们的爬网程序最近访问该网页的时间)的快照。此页面版本用于对您的搜索结果进行评级。该页面自上次对其进行缓存以来可能已更改。若要查看已更改的内容(不包含突出显示)，请转到当前页面。
您搜索的内容: ssr 一键安装 我们突出显示了在以下页面中出现的匹配词。
必应不对此页面的内容负责。
秋水逸冰
首页
文学
相册
关于

输入关键字搜索
你的位置：秋水逸冰 > 技术 > Shadowsocks 一键安装脚本（四合一）
Shadowsocks 一键安装脚本（四合一）
技术	秋水逸冰 发布于: 2016-12-04 更新于: 2019-01-11 1575666 次围观 1277 次吐槽
Shadowsocks一键安装脚本（四合一版）

本脚本适用环境
系统支持：CentOS 6+，Debian 7+，Ubuntu 12+
内存要求：≥128M
日期　　：2019 年 01 月 11 日

关于本脚本
1、一键安装 Shadowsocks-Python， ShadowsocksR， Shadowsocks-Go， Shadowsocks-libev 版（四选一）服务端；
2、各版本的启动脚本及配置文件名不再重合；
3、每次运行可安装一种版本；
4、支持以多次运行来安装多个版本，且各个版本可以共存（注意端口号需设成不同）；
5、若已安装多个版本，则卸载时也需多次运行（每次卸载一种）；

友情提示：如果你有问题，请先阅读这篇《Shadowsocks Troubleshooting》之后再询问。


默认配置
服务器端口：自己设定（如不设定，默认从 9000-19999 之间随机生成）
密码：自己设定（如不设定，默认为 teddysun.com）
加密方式：自己设定（如不设定，Python 和 libev 版默认为 aes-256-gcm，R 和 Go 版默认为 aes-256-cfb）
协议（protocol）：自己设定（如不设定，默认为 origin）（仅限 ShadowsocksR 版）
混淆（obfs）：自己设定（如不设定，默认为 plain）（仅限 ShadowsocksR 版）
备注：脚本默认创建单用户配置文件，如需配置多用户，请手动修改相应的配置文件后重启即可。

客户端下载
常规版 Windows 客户端
https://github.com/shadowsocks/shadowsocks-windows/releases

ShadowsocksR 版 Windows 客户端
https://github.com/shadowsocksrr/shadowsocksr-csharp/releases

使用方法
使用root用户登录，运行以下命令：

wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
安装完成后，脚本提示如下
Congratulations, your_shadowsocks_version install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Encryption Method:your_encryption_method

Your QR Code: (For Shadowsocks Windows, OSX, Android and iOS clients)
 ss://your_encryption_method:[email protected]_server_ip:your_server_port
Your QR Code has been saved as a PNG file path:
 your_path.png

Welcome to visit:https://teddysun.com/486.html
Enjoy it!
卸载方法
若已安装多个版本，则卸载时也需多次运行（每次卸载一种）

使用root用户登录，运行以下命令：

./shadowsocks-all.sh uninstall
启动脚本
启动脚本后面的参数含义，从左至右依次为：启动，停止，重启，查看状态。

Shadowsocks-Python 版：
/etc/init.d/shadowsocks-python start | stop | restart | status

ShadowsocksR 版：
/etc/init.d/shadowsocks-r start | stop | restart | status

Shadowsocks-Go 版：
/etc/init.d/shadowsocks-go start | stop | restart | status

Shadowsocks-libev 版：
/etc/init.d/shadowsocks-libev start | stop | restart | status

各版本默认配置文件
Shadowsocks-Python 版：
/etc/shadowsocks-python/config.json

ShadowsocksR 版：
/etc/shadowsocks-r/config.json

Shadowsocks-Go 版：
/etc/shadowsocks-go/config.json

Shadowsocks-libev 版：
/etc/shadowsocks-libev/config.json

更新日志
2019 年 01 月 11 日：
1、升级：libsodium 到最新版本 1.0.17；
2、升级：mbedtls 到最新版本 2.16.0；

2018 年 11 月 05 日：
1、升级：使用 Github 上最新代码编译出 Go 版二进制可执行文件，版本号 1.2.2。

2018 年 06 月 01 日：
1、修正：在启用了插件 simple-obfs 的情况下，libev 版启动失败的问题；
2、修正：在使用 /etc/init.d/shadowsocks-libev restart 命令重启 libev 版服务端时，偶尔出现的 “bind: Address already in use” 问题；
3、修正：移除 libev 版配置文件中的 local_address 字段；
4、修改：不再默认使用 root 用户启动，改为使用 nobody 用户启动 libev 版服务端 ss-server；
5、升级：mbedtls 到版本 2.9.0；
6、修改：libev 版启动脚本中的 -u 参数（即同时启用 TCP 和 UDP 模式），改到配置文件里配置为 “mode”: “tcp_and_udp”；
7、修改：libev 版配置文件的内置 NameServers 为 8.8.8.8，默认是从 /etc/resolv.conf 中取得。

2018 年 02 月 07 日：
1、修改：将默认端口从 8989 改为从 9000-19999 之间随机生成。

2018 年 02 月 06 日：
1、修改：ShadowsocksR 版为 ShadowsocksRR 最新版；
2、新增：ShadowsocksR 版的协议（protocol）增加了 4 个，分别为：

auth_chain_c
auth_chain_d
auth_chain_e
auth_chain_f
2017 年 12 月 29 日：
1、升级：libsodium 到 1.0.16。

2017 年 11 月 25 日：
1、如果 Linux 内核版本大于 3.7.0，则配置文件默认支持 TCP fast open；
2、新增：libev 版启动时支持 verbose mode，也就是默认写 log 到 /var/log/messages 方便查看。

2017 年 11 月 12 日：
1、新增生成 ss:// 或 ssr:// 链接，以及其二维码图片。
※ 脚本会根据当前安装的版本以及输入的各项配置，自动生成 ss:// 或 ssr:// 的链接并在安装成功后显示，直接复制即可被客户端识别。同时生成其二维码图片，并保存在当前目录下，下载后用看图软件打开，也能被客户端识别。

复制二维码链接后 Shadowsocks 客户端识别示例：
Shadowsocks 客户端示例

复制二维码链接后 ShadowsocksR 客户端识别示例：
ShadowsocksR 客户端示例

二维码（QR Code）参考链接：
https://github.com/shadowsocks/shadowsocks/wiki/Generate-QR-Code-for-Android-or-iOS-Clients
https://github.com/shadowsocksr-backup/shadowsocks-rss/wiki/SSR-QRcode-scheme

2017 年 10 月 22 日：
1、升级：libsodium 到 1.0.15。

2017 年 10 月 14 日：
1、新增：在安装 Shadowsocks-libev 版时可选安装 simple-obfs 服务端。
※ 脚本通过判断 autoconf 版本是否大于或等于 2.67 来一键安装 simple-obfs 服务端。并且，支持在安装过程中选择 obfs 为 http 或 tls。
※ 使用方法参考：https://teddysun.com/511.html

2017 年 09 月 16 日：
1、修正：Shadowsocks-libev 版 v3.1.0 使用 libc-ares 替换 libudns 依赖包，解决了依赖问题；
2、升级：mbedtls 到版本 2.6.0。

2017 年 07 月 27 日：
1、新增：ShadowsocksR 版可选协议（protocol）auth_chain_b 。使用该协议需更新到最新（4.7.0） ShadowsocksR 版客户端；
2、修改：更新 ShadowsocksR 源码下载地址。

2017 年 07 月 23 日：
1、修正：卸载时可自行选择某个版本卸载，若该版本不存在则报错退出。

2017 年 07 月 22 日：
1、修正：默认加密方式从 aes-256-cfb 改为 aes-256-gcm（Python 和 libev 版）；
2、新增：安装时可选 16 种加密方式的其中之一（Python 和 libev 版）。如下所示：

aes-256-gcm
aes-192-gcm
aes-128-gcm
aes-256-ctr
aes-192-ctr
aes-128-ctr
aes-256-cfb
aes-192-cfb
aes-128-cfb
camellia-128-cfb
camellia-192-cfb
camellia-256-cfb
chacha20-ietf-poly1305
chacha20-ietf
chacha20
rc4-md5
3、新增：安装时可选 9 种加密方式的其中之一（Go 版）。如下所示：

aes-256-cfb
aes-192-cfb
aes-128-cfb
aes-256-ctr
aes-192-ctr
aes-128-ctr
chacha20-ietf
chacha20
rc4-md5
4、新增：安装时可选 15 种加密方式的其中之一（none 是不加密，ShadowsocksR 版）。如下所示：

none
aes-256-cfb
aes-192-cfb
aes-128-cfb
aes-256-cfb8
aes-192-cfb8
aes-128-cfb8
aes-256-ctr
aes-192-ctr
aes-128-ctr
chacha20-ietf
chacha20
salsa20
xchacha20
xsalsa20
rc4-md5
5、新增：安装时可选 7 种协议（protocol）的其中之一（仅限 ShadowsocksR 版）。如下所示：

origin
verify_deflate
auth_sha1_v4
auth_sha1_v4_compatible
auth_aes128_md5
auth_aes128_sha1
auth_chain_a
auth_chain_b
6、新增：安装时可选 9 种混淆（obfs）的其中之一（仅限 ShadowsocksR 版）。如下所示：

plain
http_simple
http_simple_compatible
http_post
http_post_compatible
tls1.2_ticket_auth
tls1.2_ticket_auth_compatible
tls1.2_ticket_fastauth
tls1.2_ticket_fastauth_compatible
2017 年 02 月 24 日：
1、恢复： 通过 Github API 自动获取 Shadowsocks-libev 的最新 release 版本的功能（v3.0.3）。

2017 年 02 月 13 日：
1、升级： Shadowsocks-libev 版到版本 3.0.2；
2、升级： Shadowsocks-go 版到版本 1.2.1（基于 Github 最新代码，用 go 1.8 编译完成的 x86 和 x86_64 二进制文件）；
3、修复：在 Debian 7 下默认没有 libudns-dev 依赖包的问题。

2017 年 02 月 12 日：
1、升级： Shadowsocks-libev 版到版本 3.0.1。

2017 年 01 月 27 日：
1、升级： Shadowsocks-go 版到版本 1.2.1 （仅适用于 x86_64 系统）

更多单版本 Shadowsocks 服务端一键安装脚本
Shadowsocks Python 版一键安装脚本（CentOS，Debian，Ubuntu）
ShadowsocksR 版一键安装脚本（CentOS，Debian，Ubuntu）
CentOS 下 Shadowsocks-libev 一键安装脚本
Debian 下 Shadowsocks-libev 一键安装脚本
Shadowsocks-go 一键安装脚本（CentOS，Debian，Ubuntu）

注意：以上单版本不可与该四合一版本混用。

转载请注明：秋水逸冰 » Shadowsocks 一键安装脚本（四合一）

继续浏览有关 CentOSDebianshadowsocksShell 的文章
上一篇 FTP 上传一键脚本ftp_upload.sh 一键安装最新内核并开启 BBR 脚本 下一篇
与本文相关的文章
介绍几款 Docker 镜像
如何启用 Shadowsocks 的多端口
使用定时任务cron监视Shadowsocks进程
如何安装和配置simple-obfs服务端
CentOS 6.10安装Python2.7.15
一键脚本那些事儿
一键测试脚本bench.sh
解决pip安装M2Crypto失败的问题
在CentOS下编译安装GCC
LAMP一键安装脚本使用说明
如何在Debian下安装Webmin
Shadowsocks Troubleshooting

发表评论
取消评论
昵称
昵称
昵称 (必填)
邮箱
邮箱
邮箱 (必填)
网址
网址
网址

写点什么...
 提交评论
表情  有人回复时邮件通知我
已有评论 (1277)

IPv6 support Traceback (most recent call last): File "/usr/local/shadowsocks/server.py", line 221, in main() File "/usr/local/shadowsocks/server.py", line 39, in main config = shell.get_config(False) File "/usr/local/shadowsocks/../shadowsocks/shell.py", line 303, in get_config check_config(config, is_local) File "/usr/local/shadowsocks/../shadowsocks/shell.py", line 132, in check_config encrypt.try_cipher(config['password'], config['method']) File "/usr/local/shadowsocks/../shadowsocks/encrypt.py", line 46, in try_cipher Encryptor(key, method) File "/usr/local/shadowsocks/../shadowsocks/encrypt.py", line 91, in __init__ random_string(self._method_info[1])) File "/usr/local/shadowsocks/../shadowsocks/encrypt.py", line 110, in get_cipher key, iv_ = EVP_BytesToKey(password, m[0], m[1], self.cache) File "/usr/local/shadowsocks/../shadowsocks/encrypt.py", line 63, in EVP_BytesToKey md5.update(data) TypeError: must be string or buffer, not dict Starting ShadowsocksR failed 请问这种问题应该怎么解决啊？
Cyanmon2周前 (2019-01-16)回复

什么时候升级下，支持新版v2ray-plugin。
kixo2周前 (2019-01-15)回复

试了下最新的脚本，一直保持 LC_CTYPE: cannot change locale (UTF-8): No such file or directory
young2周前 (2019-01-14)回复

请问是否支持centos7，我在7上面安装成功了，客户端能连接，但是无法上网。
shading4周前 (2019-01-06)回复

你好 搭建好后 安卓手机链接后外网浏览正常，就是谷歌商店的app怎么也下载不下来，是因为什么呢？ 软件一直停在 正在等待下载，就没有下文了。。。。
jack tt4周前 (2019-01-06)回复

没文化真是不行啊 搬瓦工自带的centos 不带下载命令 会提示wget command not found 用yum -y install wget 开启就好了
rzgz750691个月前 (2018-12-27)回复

[Info] Checking the EPEL repository... [Info] Checking the EPEL repository complete... [Info] Starting to install package unzip [Info] Starting to install package gzip [Error] Failed to install gzip 秋大这个咋决解啊。。
Mr.Lin1个月前 (2018-12-27)回复

我是用Putty安装shadowsocks的python客户端两次，都遇到了Install EPEL repo failed, please check it这个报错，后来通过谷歌查到https://www.tecmint.com/how-to-enable-epel-repository-for-rhel-centos-6-5/ 的回答，复制粘贴如下命令，运行后就不会再报错了：## RHEL/CentOS 7 64-Bit ## # wget http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm # rpm -ivh epel-release-latest-7.noarch.rpm
hereticalcoral1个月前 (2018-12-29)回复

希望秋水大佬能修改下脚本SSRR的服务端拉取版本 恢复auth_chain_e / f 协议正常连接
落叶1个月前 (2018-12-24)回复

国内的vps无法装..地址被屏蔽了
watchasss1个月前 (2018-12-22)回复

秋水大佬，打扰你了。小白来问个问题。在你四合一版本里面的，SS--Python版本，配置多用户，怎么修改配置文件，我试过不行。看提示是说我，用户之间的标点符号有问题，那应该用什么符号，求指导。谢谢大佬
Jackie1个月前 (2018-12-22)回复

部分VPS会出现安装完成无法使用的情况，centOs 7安装一键脚本，安装之前记得 先执行 yum install firewalld systemctl start firewalld
does1个月前 (2018-12-19)回复

firewalld 在 CentOS 7 下是默认安装的。而且这一步也是非必要的。
秋水逸冰1个月前 (2018-12-19)回复

一键脚本正常安装， 通过脚本生成的ss:xxx 直接生成的配置进行连接，不能用。 有人遇到这种情况吗？ vps是centOs 6 32， client mac 10.13.3
does1个月前 (2018-12-19)回复

客户端怎么配置？尤其是obfs和代理端口？
小二黑1个月前 (2018-12-19)回复

秋水你好，四合一脚本安装的ShadowsocksR和“ShadowsocksR一键安装脚本”的SSR在服务器端安装完成后 ,客户端都无法使用 auth_chain_e / f 两种协议，似乎是akkariiin更新了什么导致脚本调用出错，希望能修复一下
落叶1个月前 (2018-12-18)回复

查看了issues有人反映是服务端SSRR 3.2.2存在不能使用auth_chain_e / f协议的BUG （https://github.com/shadowsocksrr/shadowsocksr/issues/40 https://github.com/shadowsocksrr/shadowsocksr/issues/72） 使用SSRR 3.2.1 则能恢复auth_chain_e / f的正常连接 （https://github.com/shadowsocksrr/shadowsocksr/issues/27）
落叶1个月前 (2018-12-24)回复
1 … 55 56 57
推荐资源
CSR 在线生成工具
L2TP 一键安装脚本
LAMP 一键安装脚本
Bench 一键测试脚本
Shadowsocks 免费帐号
Shadowsocks-Go 一键脚本
ShadowsocksR 一键安装脚本
Shadowsocks-Python 一键脚本
Shadowsocks 一键脚本（四合一）
Shadowsocks-libev for Debian 一键脚本
Shadowsocks-libev for CentOS 一键脚本
Shadowcosks推荐
getss 
稳定可靠的 Shadowsocks 服务，其服务器分布于：
美国，俄罗斯，日本，韩国，新加坡，香港，台湾。
同时兼容 SS 和 SSR 客户端连接。
最低只需 1 元 1GB 3 天，先体验再付费。
经典VPS
bandwagonhost 
使用优惠码 BWH26FXH3HIQ 后仅需$18.79/年起
vultr 
15个数据中心，低至$2.5/月，新用户注册就送$10
digitalocean 
1GB内存，25G SSD，$5/月，新用户注册就送$10
ramnode 
经典Linode，新用户优惠码podcastinit2018，充$5送$20
标签云
VPS (22)CentOS (21)Linux (16)shadowsocks (13)apache (11)PHP (10)wordpress (9)LAMP (9)web (9)Google (8)Shell (6)Google Drive (5)网络安全 (5)Windows (5)VPN (4)DigitalOcean (4)webmin (4)网盘 (4)Debian (4)ssl (4)domain (4)Python (3)iptables (3)电影 (3)ownCloud (3)eclipse (3)phpMyAdmin (3)pip (3)PPTP (2)L2TP (2)生活 (2)JDK7 (2)
最新文章
介绍几款 Windows DD 镜像
如何制作 Windows Server 2019 的 DD 镜像
介绍几款 Docker 镜像
如何启用 Shadowsocks 的多端口
一键安装KMS服务脚本
关于免费SSL证书的那些事儿
使用定时任务cron监视Shadowsocks进程
LAMP新增Letsencrypt支持
© 2013-2019 秋水逸冰 Powered by WordPress & Linode Theme D8
