---
layout: post
title:  "给github、gitee同时配置ssh key"
subtitle:   git的某方面使用心得
date:   2020-05-21
author:   tanzhaaa
header-img: img/post-bg-debug.png
catalog: true
tags:
tags: 
    - git  
---

* content
{:toc}


~~因为有时github登录太慢了~~

第一步：切换目录：
=================
    cd ~/.ssh

第二步：通过下面的命令，依次生成两个平台的key
===================
~~因为github之前占用了默认的名字就不给它改了~~

```
$ ssh-keygen -t rsa -C "xxxxxxx@qq.com" -f "id_rsa"
$ ssh-keygen -t rsa -C "xxxxxxx@qq.com" -f "id_rsa--gitee"
```

第三步：将SSH Key粘贴到对应网站(GitHub，gitee)
=============
    clip < ~/.ssh/id_rsa.pub


第四步：创建配置文件解决SSH冲突
================
在.ssh文件夹下执行命令```vi config```  
文件中添加以下内容  

```
# gitee
Host gitee.com
HostName gitee.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa_gitee

# github
Host github.com
HostName github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa  # github 使用默认名
```

第五步：测试连接是否可用
==============
执行    
```ssh -T git@gitee.com```  
成功则返回    
```Welcome to Gitee.com ,tanzhaaa!```    
执行  
```ssh -T git@github.com```  
成功则返回    
```Hi tanzhaaa! You've successfully authenticated, but GitHub does not provide shell access.```  

第六步：结语
================
到此，本文件可以同时上传到gitee和GitHub  
~就用上传这个文件来试试~  
成功了！！！而且上传速度快多了  
但是好像gitee上不能正确显示*样式* ，<u>待解决</u>  

