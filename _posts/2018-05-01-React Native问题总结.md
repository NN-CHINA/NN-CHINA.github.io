---
title: React Native问题总结   
date: 2018-05-01  
categories: ReactNative  

---


1. “RCTBundleURLProvider.h” file not found

		解决方法：
		- 打开Mac里面的终端，进入项目所在的文件夹目录；
		- 把项目里面的 node_modules 文件夹删除掉，然后执行  npm install 命令
		- npm install安装完成后， 执行react-native upgrade命令
		最后重新打开Xcode,clean一下

2. xcode 'boost/config/user.hpp' file not found  

		解决方法：
		rm -r ~/.rncache  
		rm -r <your-project>/node_modules/react-native/third_party