---
title: React Native遇到的问题.  
categories: React Native.  
tags: React Native.  

---

1. Xcode运行时一直indexing，且卡在运行自定义脚本处；
		
		RN iOS 0.45以上版本开始需要依赖一些第三方编译库, 
		~/.rncache目录下补全需要的文件，
		具体参考：[文档](https://reactnative.cn/blog.html)

2. Connection to http://xxx.xxx.xxx.xxx:8081/debugger-proxy?role=client timed out. Are you running node proxy? If you are running on the device, check if you have the right IP address in `RCTWebSocketExecutor.m`.

		
