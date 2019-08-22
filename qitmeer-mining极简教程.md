# Qitmeer挖矿极简教程

本教程适用于不喜欢自己编译miner的用户

## 第一步：下载挖矿程序 miner包

下载官方已编译好的 miner包：点击 [此处下载](https://github.com/Qitmeer/qitmeer-miner/releases)

在`Assets`选择适合自己系统的 miner包：

![image](https://user-images.githubusercontent.com/32875657/63500461-74175680-c4fc-11e9-9ac8-7cc67c0bb337.png)

将下载好的 miner 包解压，会得到一个名为 xxx-miner 的文件夹，例如 windows-miner，为方便后边描述，姑且将该 xxx-miner文件夹 存放于 D 盘。

## 第二步：修改 miner包中的配置文件 `qitmeer.conf`

在下载的miner包中有两个文件，一个是 miner执行程序 `qitmeer-miner`；一个是配置文件 `qitmeer.conf`

配置文件中主要有两部分是我们需要修改的部分：

![conf](https://user-images.githubusercontent.com/32875657/63501669-a1fd9a80-c4fe-11e9-8cb6-b57c321e949f.png)

- 第一个是：# [solo config]

  这个是独立挖矿配置，主要修改四个配置：
  
  - 挖矿地址：mineraddress=RmN4SADy42FKmN8ARKieX9iHh9icptdgYNn（此地址可以从[cahf钱包](http://www.kahf.io/)中获得）
  
  - 全节点服务器IP及端口：rpcserver=127.0.0.1:1234（这是你自己的全节点ip及端口，端口通常会用1236）
  
  - 全节点连接用户名配置：rpcuser=test（这是你自己的全节点rpc用户名，通常是admin）
  
  - 全节点连接密码配置：rpcpass=test（这里是你自己的全节点rpc连接密码）
  
- 第二个是：# [pool config]

  这是连接矿池挖矿需要的配置，主要有两个参数：
  
  - 矿池连接地址：pool=stratum+tcp://47.93.20.102:3176（你要连接的矿池地址，矿池推广主页会给出）
  
  - 挖矿地址：pooluser=TmbCBKbZF8PeSdj5Chm22T4hZRMJY5D8XyX（配置自己的挖矿地址，可以从[cahf钱包](http://www.kahf.io/)中获得）
  
  
## 第三步：启动程序挖矿

此处以 windows 系统下的操作为例。

 1. 使用 win+R 组合键 打开`运行`，输入 cmd 打开命令行窗口
 
 2. 首先要在命令行窗口下进入到 windows-miner文件夹：

  - 输入命令 `d：`先进入到d盘下
  - 输入命令 `cd windows-miner` 打开存放挖矿程序的文件夹
  
  3. 输入命令：`windows-miner -C qitmeer.conf` 调用本地配置文件 qitmeer.conf 开启挖矿
  
  ![mining2](https://user-images.githubusercontent.com/32875657/63503357-e3dc1000-c501-11e9-8f44-529dabfd4e37.PNG)
  
  4. 退出挖矿：使用组合按键 `Ctrl+C`



