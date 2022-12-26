---
layout:     post
title:      Linux C++开发环境搭建
subtitle:   
date:       2022-12-26
author:     Keep Loading
header-img: img/post-bg-article.jpg
catalog: true
tags:
    - Linux
---
<a name="vuACD"></a>
# 开发软件一览
1. ubuntu 14.04 LTS 
2. VSCode 1.70.1 
<a name="cc0jh"></a>
# 在VM虚拟机安装ubuntu
<a name="C3A1G"></a>
## 下载VM
[在VMWare官网下载](https://www.vmware.com/cn/products/workstation-pro.html)，跳转至下载页面<br />![vmware download.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672061759540-63355c25-b661-4a58-9965-57ef079463bb.png#averageHue=%23dfeec9&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=384&id=uaf9a21a2&margin=%5Bobject%20Object%5D&name=vmware%20download.png&originHeight=384&originWidth=1418&originalType=binary&ratio=1&rotation=0&showTitle=false&size=59656&status=done&style=none&taskId=uf185b94e-710e-4a87-8d01-deb0bf8cbfb&title=&width=1418)<br />![vmware download2.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672061766312-28062e0a-e964-49cd-93fb-fe7cc60d0271.png#averageHue=%23e6e5d0&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=586&id=uefaa577b&margin=%5Bobject%20Object%5D&name=vmware%20download2.png&originHeight=586&originWidth=1349&originalType=binary&ratio=1&rotation=0&showTitle=false&size=221662&status=done&style=none&taskId=u5aebd0d2-9139-4757-ab4b-6546d9b09ef&title=&width=1349)
<a name="Q8d3q"></a>
## 安装VM
打开下载好的 .exe 文件， 即可开始安装。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672061920018-f5e20b0f-acbd-41a5-ac1a-9a4509a4a747.png#averageHue=%23e4e3e3&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=u6484f866&margin=%5Bobject%20Object%5D&name=image.png&originHeight=530&originWidth=658&originalType=url&ratio=1&rotation=0&showTitle=false&size=98082&status=done&style=none&taskId=u2a4523f7-e7a3-40eb-82b4-36cd45a5ffb&title=)<br />一直点击 下一步 等待软件安装完成。
<a name="IzHMc"></a>
## 在VM安装ubuntu
打开VM<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672062141206-990e3dad-086d-401e-8235-719f3b82939b.png#averageHue=%23fafaf9&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=u79c5b031&margin=%5Bobject%20Object%5D&name=image.png&originHeight=796&originWidth=1527&originalType=url&ratio=1&rotation=0&showTitle=false&size=98338&status=done&style=none&taskId=uad694323-2073-448a-9e9e-bf51aa00a5a&title=)<br />[在ubuntu官网下载ubuntu镜像](https://ubuntu.com/)<br />![ubuntu.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672062388448-8a67ac1e-5a51-41e6-8c1e-a1b975b620c4.png#averageHue=%23373433&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6b744f97&margin=%5Bobject%20Object%5D&name=ubuntu.png&originHeight=454&originWidth=1338&originalType=binary&ratio=1&rotation=0&showTitle=false&size=116641&status=done&style=none&taskId=u03b928ed-7a19-4f8e-aff8-6ad6a948d4c&title=)<br />在vm创建新的虚拟机<br />![1672062448036.jpg](https://cdn.nlark.com/yuque/0/2022/jpeg/2342281/1672062462993-3160f9ae-7156-46d9-b50b-5c6f0641645c.jpeg#averageHue=%23f3f1f1&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=440&id=u726cd487&margin=%5Bobject%20Object%5D&name=1672062448036.jpg&originHeight=440&originWidth=513&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42476&status=done&style=none&taskId=uce6286a9-f91b-4880-a904-d8b57a4cc23&title=&width=513)<br />一直点击 下一步 直到为虚拟机分配磁盘大小，建议给磁盘大小设置的大一些，因为我们会在linux上下载各种软件。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672062544580-6f427bf6-4c09-40a6-b3db-2164ecc45cfa.png#averageHue=%23eaeaea&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=uc89ad064&margin=%5Bobject%20Object%5D&name=image.png&originHeight=551&originWidth=570&originalType=url&ratio=1&rotation=0&showTitle=false&size=28931&status=done&style=none&taskId=ue08d030a-1a16-4c4f-b91e-caf851bf5b8&title=)<br />点击自定义硬件，内存建议8G<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672062658370-dab9d989-9254-44a5-9221-54edf940ee7e.png#averageHue=%23f9f9f8&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=uf6cd42dd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=966&originWidth=860&originalType=url&ratio=1&rotation=0&showTitle=false&size=64256&status=done&style=none&taskId=ubfe4fb6a-16c6-4da9-8196-53b92c783c0&title=)<br />网络适配器选择桥接模式<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672062705684-112abb3e-c7f1-4f91-b220-5cb33ee306de.png#averageHue=%23f8f7f7&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=u525eae6d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=966&originWidth=860&originalType=url&ratio=1&rotation=0&showTitle=false&size=64395&status=done&style=none&taskId=u37506efb-d784-4f89-9d96-af1b5507bc7&title=)<br />使用ISO映像文件，点击浏览，选择刚刚下载好的Ubuntu系统镜像的压缩包<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672062729899-23b60c60-7b4f-49e8-b939-0ca1f85acf52.png#averageHue=%23f9f9f9&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=u9b5f784d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=966&originWidth=860&originalType=url&ratio=1&rotation=0&showTitle=false&size=58806&status=done&style=none&taskId=uadbad5d2-2073-4500-9f6a-9b3e7d47e5a&title=)<br />运行虚拟机，安装ubuntu，只要根据指示进行配置就可以了，ubuntu就安装完成了。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672062854582-a4ac9e08-7c96-4f99-9911-4d3f586dc582.png#averageHue=%232d345b&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=926&id=ua06af729&margin=%5Bobject%20Object%5D&name=image.png&originHeight=926&originWidth=1718&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1400178&status=done&style=none&taskId=uec583cbf-11ca-4dcc-bd04-2f2476890f9&title=&width=1718)
<a name="kQLqj"></a>
# 安装VSCode
<a name="UHV30"></a>
## VSCode下载
进入VSCode官网[Visual Studio Code - Code Editing. Redefined](https://code.visualstudio.com/)进行下载。
<a name="NlRFb"></a>
## 安装VSCode
下载完后，点击安装包进行安装，安装完后界面如下：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672063343898-78ed2413-1bc9-4e5b-ac2f-7d40665f9dfa.png#averageHue=%232d2d2d&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=u7039670b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=805&originWidth=1028&originalType=url&ratio=1&rotation=0&showTitle=false&size=114540&status=done&style=none&taskId=uc6e47615-6989-4bbf-9ab3-e3dad1b0a09&title=)
<a name="fWjFp"></a>
## 配置C/C++环境
<a name="P6bFl"></a>
### 安装g++
```
sudo apt install g++
```
<a name="oqPiz"></a>
## 安装vim
```
sudo apt install vim
```
<a name="k5i8v"></a>
### 安装汉化、C++插件
在左侧扩展商店中查找 ”chinese“选第一个安装，安装好后重启软件。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672063612583-0a6510fa-df2a-4aef-95f7-19dd39ab69fb.png#averageHue=%23252423&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=973&id=u36f2dddf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=973&originWidth=1861&originalType=binary&ratio=1&rotation=0&showTitle=false&size=218484&status=done&style=none&taskId=u2d3fe68f-b2fc-4e83-926c-a647a93f318&title=&width=1861)<br />在左侧扩展商店中查找 ”C/C++“选第一个安装。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672063678383-2729e203-9d1d-4de2-b01a-bffaa9b5d42c.png#averageHue=%23293037&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=980&id=u465308c4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=980&originWidth=303&originalType=binary&ratio=1&rotation=0&showTitle=false&size=116461&status=done&style=none&taskId=uf1f53a16-84d7-4555-9774-79b11617952&title=&width=303)
<a name="sK4mB"></a>
# 远程连接ssh
虚拟机安装ssh服务
```
sudo apt install openssh-server
```
vscode安装remote-SSH插件<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672064585406-9d108179-5357-44cd-b31b-45fbdc47e9d7.png#averageHue=%23292d32&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=907&id=u32b47363&margin=%5Bobject%20Object%5D&name=image.png&originHeight=907&originWidth=292&originalType=binary&ratio=1&rotation=0&showTitle=false&size=96231&status=done&style=none&taskId=u30b0b5d8-08f1-44c4-a75c-5c8620345a1&title=&width=292)<br />打开Remote-SSH配置文件<br />vscode中使用快捷键Ctrl + shift + p输入remote-ssh选择Open SSH Configration File<br />配置ip端口和虚拟机登录用户名<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672064664842-549e44c8-f385-4eac-adf7-3ec6f92e6f9b.png#averageHue=%23282822&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=294&id=u7dd6c2d9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=294&originWidth=515&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9476&status=done&style=none&taskId=ucd994a5e-defc-4bd5-bd11-a318ce5b430&title=&width=515)<br />vscode中使用快捷键Ctrl + shift + p输入remote-ssh选择Connect to Host…，选择你设置的远程连接名称<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2342281/1672064691712-acd12856-c166-4f5c-bb4d-3907c71810b3.png#averageHue=%23393931&clientId=u77c0cd5f-771e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=133&id=u73390c65&margin=%5Bobject%20Object%5D&name=image.png&originHeight=133&originWidth=593&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6202&status=done&style=none&taskId=u1933c813-a24a-470b-a1ef-914e650a482&title=&width=593)
