# docker
docker 从开始到放弃

## docker 安装 -- MacOs

### 使用 Homebrew 安装

  Homebrew 的 Cask 已经支持 Docker for Mac，因此可以很方便的使用 Homebrew Cask 来进行安装

  ```
    $ brew cask install docker
  ```

  在载入 Docker app 后，点击 Next，可能会询问你的 macOS 登陆密码，你输入即可。之后会弹出一个 Docker 运行的提示窗口，状态栏上也有有个小鲸鱼的图标。


### 手动下载安装
  朕安装用的是这个种方法 （朕比较笨）

  手动下载地址 http://get.daocloud.io/#install-docker-for-mac-windows
  下载 --> 双击 `.dmg` 安装 --> 运行

  点击顶部状态栏中的鲸鱼图标会弹出操作菜单

  启动终端后，通过命令可以检查安装后的 Docker 版本。

  ```
    $ docker --version 或 $ docker -v
  ```

  出现

  ```
    Docker version 19.03.2, build 6a30dfc
  ```
  说明安装成功


## 镜像加速

  鉴于国内网络问题，后续拉取 Docker 镜像十分缓慢，我们可以需要配置加速器来解决，我使用的是网易的镜像地址：http://hub-mirror.c.163.com。

  在任务栏点击 Docker for mac 应用图标 -> Perferences... -> Daemon -> Registry mirrors。在列表中填写加速器地址即可。修改完成之后，点击 Apply & Restart 按钮，Docker 就会重启并应用配置的镜像地址了。


  通过 docker info 来查看是否配置成功

  ```
    $ docker info
  ```

  ## docker 常用命令

  [docker command](./docker-commad.md)


