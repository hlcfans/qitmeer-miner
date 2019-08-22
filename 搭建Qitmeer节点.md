## Building qitmeer node as a server 【qitmeer节点搭建；自己编译节点文件】

搭建 Qitmeer 全节点，你可能需要租赁一个云服务器，去阿里云或者亚马逊等

### Env preparation (环境准备)

- install [git](https://git-scm.com/downloads)  【安装git】

- Update Go to version at least 1.12 (required >= 1.12)  【安装go环境，版本至少1.12】

  - install [go](http://www.runoob.com/go/go-environment.html) 【go安装包下载】

  - Check your golang version  【go 版本检测】
  
  ```bash
   ~ go version
   go version go1.12 darwin/amd64 
  ```

### How to build 【建立qitmeer节点程序】

#### build node 【建立节点】

- clone qitmeer repo 【克隆qitmeer仓库到本地】

  - `git clone https://github.com/HalalChain/qitmeer.git`
  
   - maybe need Personal access tokens: [setting GitHub token](https://github.com/settings/tokens) 【克隆时需要输入你的github账户的token密钥】

- `cd qitmeer` ，then `go build` qitmeer 【打开本地的qitmeer仓库，使用“go build”命令编译qitmeer】

- run qitmeer using the command `./qitmeer` 【输入“./qitmeer”运行qitmeer】 

  - this will creat a directory named `.qitmeerd`,and at the same time may report errors, you need stop qitmeer use `ctrl+c`   
    初次使用因为在运行qitmeer时新创建的一个名为`.qitmeerd`的文件夹中还没有 qitmeerd.conf 配置文件，因此会报错，先用`Ctrl+C`退出运行

  - then you need put the configuration file `qitmeerd.conf` into `.qitmeerd` directory, after that, run `./qitmeer` again    
    将配置文件 `qitmeerd.conf` 放到文件夹 `.qitmeerd` 中，然后再回到qitmeer文件夹下使用命令`./qitmeer`运行qitmeer
     
- setting `qitmeerd.conf`【配置文件可以自己创建，主要有下面几项】

```
testnet=1
rpcuser=xxxxx(e.g. admin)
rpcpass=xxxxxx
rpclisten=0.0.0.0:1236

#miningaddr=NmWxbLp6fk3VE2sG55txAeCZpAGx7fUX3Jn
miningaddr=xxxxxxxxxxxxxxxxxxx（your addr）

notls=1
txindex=1
#generate=1
externalip=xx.xx.xxx.xxx(your server IP | 服务器IP地址)
```    

#### background running【后台运行】

- how to start qitmeer in the background 【后台运行qitmeer】

  - To start qitmeer in the background, use command ``nohup ./qitmeer >log.log 2>&1 &``, this will output logs as log.log  
    后台运行命令：``nohup ./qitmeer >log.log 2>&1 &``
  
  - view logs by using `tail -f log.log`   【查看日志】
  
  - view the qitmeer process by using `ps -ef|grep qitmeer` 【查看当前运行进程】
  
  - kill one process by using ``kill -2 <process number>`` 【关闭运行中的进程】
  
### update qitmeer local repo【更新qitmeer代码】

  - use ``git pull``, then `go build` qitmeer and run `./qitmeer` again.
  
    Before update，you need kill the qitmeer process firstly. 

    直接使用`git pull` 下载更新，然后使用 `go build` 重新编译，然后再次启动qitmeer程序即可。
    
    
    
    
##  直接下载官方打包好的节点文件建立节点

下载地址：https://github.com/Qitmeer/qitmeer/releases

下载最新版本使用。
