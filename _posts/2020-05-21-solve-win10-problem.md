---
layout: post
title:  "解决win10快速访问无法取消固定的问题"
subtitle:   问题解决方法
date:   2020-05-21
author:   tanzhaaa
header-img: img/post-bg-debug.png
catalog: true
tags: 
    - OS
---

* content
{:toc}

这几天用的Windows 10系统遇到一个莫名奇妙的问题，就是在快速访问里总是固定了下载文件夹，而且无法取消固定，其它文件夹都正常就是它不能取消固定，始终顽固的显示在快速访问里。即使我在“查看|选项|隐私"里取消对”在‘快速访问’中显示最近使用的文件”和“在‘快速访问’中显示常用文件夹”的勾选，再清除文件资源管理器历史记录最不行。    
在文件资源管理器地址栏输入：  %APPDATA%\Microsoft\Windows\Recent\AutomaticDestinations    
打开的文件夹里找到文件：f01b4d95cf55d32aautomaticDestinations-ms    
删除它，或者安全起见你可以剪切它到其它地方，再重新打开文件资源管理器，问题就这么简单的解决了：）    
