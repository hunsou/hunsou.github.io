---
layout: post
title:  "Index"
date:   2023-12-11 17:22:49 +0800
categories: Index
---

# 快速初始化工作环境

0. 浏览器
  - 个人信息缓存问题

chrome下载
https://www.google.cn/intl/en-US/chrome/?standalone=1&platform=win64  
https://www.google.cn/intl/zh-CN/chrome/?standalone=1&platform=win64  
chrome离线地址  
https://zhuanlan.zhihu.com/p/652652153  


正常使用x64
```bat
set chromedir="C:\Program Files\Google\Chrome\Application\chrome.exe"
set user-data-dir="D:\Google\ChromeUserData\User Data"
set disk-cache-dir="D:\Google\ChromeUserData\User Cache"
start "" %chromedir% --user-data-dir=%user-data-dir% --disk-cache-dir=%disk-cache-dir% --disk-cache-size=104857600
```
正常使用x86
```bat
set chromedir="C:\Program Files (x86)\Google\Chrome\Application\chrome.exe"
set user-data-dir="D:\Google\ChromeUserData\User Data"
set disk-cache-dir="D:\Google\ChromeUserData\User Cache"
%chromedir% --user-data-dir=%user-data-dir% --disk-cache-dir=%disk-cache-dir% --disk-cache-size=104857600
```
公司使用x64
```bat
set chromedir="C:\Program Files\Google\Chrome\Application\chrome.exe"
set user-data-dir="D:\Google\ChromeUserData\User Data"
set disk-cache-dir="D:\Google\ChromeUserData\User Cache"
%chromedir% -no-sandbox -incognito --user-data-dir=%user-data-dir% --disk-cache-dir=%disk-cache-dir% --disk-cache-size=104857600
```
公司使用x86
```bat
set chromedir="C:\Program Files (x86)\Google\Chrome\Application\chrome.exe"
set user-data-dir="D:\Google\ChromeUserData\User Data"
set disk-cache-dir="D:\Google\ChromeUserData\User Cache"
%chromedir% -no-sandbox -incognito --user-data-dir=%user-data-dir% --disk-cache-dir=%disk-cache-dir% --disk-cache-size=104857600
```

  - 插件下载  
  https://crxdl.com  

  - 去广告插件  
  `uBlock Origin` 去百度推荐, 广告太烦人  
  `cjpalhdlnbpafiamejdnhcphjbkeiagm`

  - github加速  
  `tampermonkey` 油猴  
  `dhdgffkkebhmkfjojejmpbldmpobfkfo`  
  https://www.tampermonkey.net/?ext=dhdg&locale=en  
  https://data.tampermonkey.net/tampermonkey_stable.crx  
  https://greasyfork.org/en/scripts/412245  

  - github镜像站重定向  
  `URLRedirector`  
  `maolmdhneopinciaokgohljhpdedekee`  


1. 解决dns问题

  - [smartdns-rs](2023-12-11-tools-smartdns.md)  
  https://github.com/mokeyish/smartdns-rs/releases


```
YWRkcmVzcyUyMC9zODUwZXZvLmNvbS8yNi41NC4xNjUuNTQlMEFhZGRyZXNzJTIwL3N0eWMuY29tLzI2LjgwLjEzNC4zMiUwQWFkZHJlc3MlMjAvc3R5YzEuY29tLzI2LjE4OS4xNzMuMjQ0JTBBYWRkcmVzcyUyMC9zdHljZmFjLmNvbS8yNi44Ni4yLjE4OSUwQWFkZHJlc3MlMjAvc3R5Y2ZhYzEuY29tLzI2LjE4MC43Mi4xODY=
```

  - dnscrypt  
  https://www.dnscrypt.org/#dnscrypt-proxy  
  https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Installation-Windows  

  - [ ] 自建ddns实现动态解析本地设备ip  

2. 解决CA问题

  - 下载自建ca并导入  

4. 文本编辑器
  - sublime  
  https://www.sublimetext.com/download  
  https://www.sublimemerge.com/download  
  sublime 设置自动保存  
  - notepad++  
  - typora  
  - obsidian  

5. 代码编辑器  

3. git工作流  

  - 不要使用账户密码方式, isa.pub可以撤销, 账户密码不能  

4. (可选)obsidian  

5. (可选)Syncthing  

