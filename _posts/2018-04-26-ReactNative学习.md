### 安装

##### Homebrew
###### Homebrew是Mac系统的包管理器，用于安装软件。
>/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

##### Node
###### Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient. Node.js' package ecosystem, npm, is the largest ecosystem of open source libraries in the world.
>brew install node  

###### 设置镜像
>npm config set registry https://registry.npm.taobao.org --global
>npm config set disturl https://npm.taobao.org/dist --global

##### Yarn、React Native的命令行工具（react-native-cli）
###### Yarn是Facebook提供的替代npm的工具，可以加速node模块的下载。React Native的命令行工具用于执行创建、初始化、更新项目、运行打包服务（packager）等任务。
>npm install -g yarn react-native-cli

###### 设置镜像
>yarn config set registry https://registry.npm.taobao.org --global   
>yarn config set disturl https://npm.taobao.org/dist --global

###### 注：`EACCES: permission denied`权限报错,修复/usr/local目录的所有权:
>sudo chown -R `whoami` /usr/local


##### Xcode
###### iOS开发

##### Watchman
######文件系统变更的工具，使packager可以快速捕捉文件的变化从而实现实时刷新。

>brew install watchman

##### [Flow](https://flow.org)

###### 静态的JS类型检查工具

> brew install flow

##### [Nuclide](https://nuclide.io)

###### 编写、运行和 调试React Native应用。

##### 测试安装
>react-native init AwesomeProject  
cd AwesomeProject  
react-native run-ios