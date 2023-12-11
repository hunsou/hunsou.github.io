---
layout: post
title:  "smartdns"
date:   2023-12-11 17:22:20 +0800
categories: tools
---

# 20231201

下载  
https://github.com/mokeyish/smartdns-rs/archive/refs/tags/0.6.5.zip  
https://github.com/mokeyish/smartdns-rs/releases/download/0.6.5/smartdns-x86_64-pc-windows-msvc.zip  
https://github.com/mokeyish/smartdns-rs/releases  

使用说明  
https://pymumu.github.io/smartdns/en/config/server-config/  
https://pymumu.github.io/smartdns/en/configuration/  
https://github.com/pymumu/smartdns/blob/doc/en/docs/configuration.md  
DOWNLOAD  
https://github.com/pymumu/smartdns/blob/doc/en/docs/download.md  
TODO  
https://github.com/mokeyish/smartdns-rs/blob/main/TODO.md  


```
./smartdns help
```

```
./smartdns service help
```

```
dig whoami ptr
```

启动脚本
```bat
@echo off
title smartdns run
:start
echo ========================smartdns start===========================
smartdns run -c test.conf -d
goto start
```

- [ ] TODO 监控文件修改,实现自动重启服务

结束脚本
```bat
@echo off
tile kill smartdns
taskkill /f /im smartdns.exe
```


检测服务有没有启动
https://github.com/mokeyish/smartdns-rs/issues/161

```
nslookup -querytype=ptr whoami.
```

```
nslookup -querytype=ptr whoami. ::1
```

```
PS C:\Users\xxx> nslookup 1.appveyor.s850evo.com
Server:  smartdns
Address:  127.0.0.1

Non-authoritative answer:
DNS request timed out.
    timeout was 2 seconds.
Name:    1.appveyor.s850evo.com
Address:  26.54.165.54
```

```
PS C:\Users\xxx> nslookup -querytype=ptr whoami.
Server:  smartdns
Address:  ::1

Non-authoritative answer:
whoami  name = smartdns
```

配置文件测试
https://github.com/mokeyish/smartdns-rs/blob/main/tests/example/smartdns.conf

```test.conf
server-name smartdns

prefetch-domain yes
serve-expired yes
cache-size 4096


# Listen on local port 53
#bind 127.0.0.1:53  
bind [::]:53
#bind :53

# Configure bootstrap-dns, if not configured, call the system_conf, 
# it is recommended to configure, so that it will be encrypted.
server 114.114.114.114
server https://1.1.1.1/dns-query  -bootstrap-dns -exclude-default-group
server https://8.8.8.8/dns-query  -bootstrap-dns -exclude-default-group

# Configure default upstream server
server https://cloudflare-dns/dns-query
server https://dns.quad9.net/dns-query
server https://dns.google/dns-query

# Configure the Office(Home) upstream server
server 192.168.1.1 -exclude-default-group -group office

# Domain names ending with ofc are forwarded to the office group for resolution
nameserver /ofc/office

# Set static IP for domain name
address /test.example.com/1.2.3.5,

# Block Domains (Ad Blocking)
address /ads.example.com/#
```



实现 SmartDNS 分组，让 DNS 解析内外完全分离
https://www.right.com.cn/FORUM/forum.php?mod=viewthread&tid=4244241&page=1&simpletype=no

https://www.right.com.cn/forum/thread-8233913-1-1.html