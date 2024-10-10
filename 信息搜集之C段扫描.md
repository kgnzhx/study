2024/10/9/23:01

# 信息搜集之C段扫描

在kali上安装masscan工具，使用该工具对IP进行扫描

## 安装masscan步骤

apt-get install git gcc make libpcap-dev

git clone https://github.com/robertdavidgraham/masscan

cd masscan

make

## 安装遇到的问题

git clone 无法访问github

1.使用网上教程，通过查github.com IP 地址及github.global.ssl.fastly.net IP地址写入本机hosts

![image-20241009231106049](C:\Users\康国宁\AppData\Roaming\Typora\typora-user-images\image-20241009231106049.png)

结果发现解决不了，哈哈哈

2.然后以为时我开了代理的问题，我将代理口改了或是关了都不行

git config --global http.proxy 127.0.0.1:xxxxx(我的代理端口号)

git config --global https.proxy 127.0.0.1:xxxxx

然后git config --global -l 验证设置

或者直接关闭代理

git config --global --unset http.proxy

git config --global --unset https.proxyv

还是结局不了问题，哈哈哈

3.之后我认为是防火墙的问题，先ping www.github.com 可以PING通，说明网络没问题。然后我关了防火墙。

ufw disable关闭防火墙后发现能下载了，问题解决了，哈哈

## messcan使用

masscan -p ip/24 --rate 10000 ->1.txt

-p 设置端口

--rate 设置发包率

-> 将扫描结果发送到1.txt

也可自定义多种格式输出

-oX 输出xml

-oJ 输出json格式

-oL 输出简单列表

--excludefile 《filename》绕过扫描特定IP，指定IP地址范围黑名单文件

我扫描我的博客地址发现扫出一个泛微登录平台，哈哈哈，忍住，不然正想测一波。

