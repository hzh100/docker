# dcoker command
dcoker 常用命令

## 安装 centos 为例
最好的学习是去实践

## docker 拉取镜像

```
  $ docker pull centos:latest
```

## 查看拉取的images

```
  $ docker images
```

## `docker run ` 运行image  (应用程序)

```
  $ docker run -i -t -d centos:latest /bin/bash
```

* docker: Docker 的二进制执行文件。

* run: 与前面的 docker 组合来运行一个容器。
  
* -d: 启动后台模式

* -t: 在新容器内指定一个伪终端或终端。

* -i: 允许你对容器内的标准输入 (STDIN) 进行交互。

* centos:latest 指定要运行的镜像，Docker 首先从本地主机上查找镜像是否存在，如果不存在，Docker 就会从镜像仓库 Docker Hub 下载公共镜像。

* /bin/bash: 在启动的容器里执行的命令

## 进入容器
在使用 -d 参数时，容器启动后会进入后台。此时想要进入容器，可以通过以下指令进入：

docker attach

docker exec：推荐大家使用 docker exec 命令，因为此退出容器终端，不会导致容器的停止

```
  $ docker attach <CONTAINER ID>
```

```
  $ docker exec -it <CONTAINER ID> /bin/bash
```

在容器中运行命令` cat /proc/version ` 和 ` ls `分别查看当前系统的版本信息和当前目录下的文件列表

## 退出容器

```
  exit 
  或
  CTRL + D
```


在容器内使用 docker logs 命令，查看容器内的标准输出：

```
  $ docker logs -f 2b1b7a428627
```

## 查看正在运行的容器

```
  $ docker ps
```

` docker ps -n 1` 或 ` docker ps -l ` 查看最近创建的一个容器

## 查看所有存在的容器

```
  $ docker ps -a
```

查看容器端口

```
  $ docker port <CONTAINER ID>
```

## 停止运行的容器

```
  $ docker stop <CONTAINER ID>
```

## 启动运行过的容器

```
  $ docker start <CONTAINER ID>
```

## 重启正在运行的容器
```
  $ docker restart <CONTAINER ID>
```
## 删除容器

```
  $ docker rm -f <CONTAINER ID>
```

## 删除镜像

```
  $ docker rm <IMAGE ID>
```

## 删除所有容器

```
  $ docker rm `docker ps -a` 
  或
  $ docker rm `docker ps -a -p` 
```

## 删除所有镜像

```
  $ docker rm `docker images -q`
```

# docker run ：创建一个新的容器并运行一个命令

```
  docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

OPTIONS说明：

  * -a stdin: 指定标准输入输出内容类型，可选 STDIN/STDOUT/STDERR 三项；

  * -d: 后台运行容器，并返回容器ID；

  * -i: 以交互模式运行容器，通常与 -t 同时使用；

  * -P: 随机端口映射，容器内部端口随机映射到主机的高端口

  * -p: 指定端口映射，格式为：主机(宿主)端口:容器端口

  * -t: 为容器重新分配一个伪输入终端，通常与 -i 同时使用；

  * --name="nginx-lb": 为容器指定一个名称；

  * --dns 8.8.8.8: 指定容器使用的DNS服务器，默认和宿主一致；

  * --dns-search example.com: 指定容器DNS搜索域名，默认和宿主一致；

  * -h "mars": 指定容器的hostname；

  * -e username="ritchie": 设置环境变量；

  * --env-file=[]: 从指定文件读入环境变量；

  * --cpuset="0-2" or --cpuset="0,1,2": 绑定容器到指定CPU运行；

  * -m :设置容器使用内存最大值；

  * --net="bridge": 指定容器的网络连接类型，支持 bridge/host/none/container: 四种类型；

  * --link=[]: 添加链接到另一个容器；

  * --expose=[]: 开放一个端口或一组端口；

  * --volume , -v: 绑定一个卷



---
# 更多精彩持续更新中......

参考 菜鸟教程 [docker 命令大全](https://www.runoob.com/docker/docker-command-manual.html)




