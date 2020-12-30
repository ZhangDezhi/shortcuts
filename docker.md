
#docker

## docker-machine 
```bash
#安装

#Linux 
$ base=https://github.com/docker/machine/releases/download/v0.16.0 &&
  curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
  sudo mv /tmp/docker-machine /usr/local/bin/docker-machine &&
  chmod +x /usr/local/bin/docker-machine
 
  #macOS
 $ base=https://github.com/docker/machine/releases/download/v0.16.0 &&
  curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/usr/local/bin/docker-machine &&
  chmod +x /usr/local/bin/docker-machine
 
  #Win(git bash)
  $ base=https://github.com/docker/machine/releases/download/v0.16.0 &&
  mkdir -p "$HOME/bin" &&
  curl -L $base/docker-machine-Windows-x86_64.exe > "$HOME/bin/docker-machine.exe" &&
  chmod +x "$HOME/bin/docker-machine.exe"

$ docker-machine version  #查看版本
$ docker-machine ls       #查看主机列表
$ docker-machine create --driver virtualbox test  #创建一台名为 test 的机器。 -driver：指定用来创建机器的驱动类型，这里是 virtualbox。
$ docker-machine create --driver=vmwareworkstation dev
$ docker-machine ip test      #查看机器的 ip
$ docker-machine stop test   #停止机器
$ docker-machine start test  #启动机器
$ docker-machine ssh test    #进入机器
$ docker-machine active       #查看当前激活状态的Docker主机
$ docker-machine config      # 查看当前激活主机连接信息
$ docker-machine rm dev      # 删除主机
```

## Docker基本操作

```bash
$ docker --version

$ docker run hello-world     #来测试从Docker Hub拉一个图像并启动一个容器
$ docker run -it ubuntu bash #运行Ubuntu容器

$ docker search httpd       # 查找镜像
$ docker pull httpd         # 下载镜像
$ docker images             # 列出本地镜像 
$ docker run httpd          # 使用镜像
$ docker rmi httpd          # 删除镜像
$ docker commit -m="提交信息" -a="zhangdezhi" e218edb10161 Dev/ubuntu:v2  | 提交镜像
$ docker build -t runoob/centos:6.7 /dockerfile/    | 构建镜像(需要dockerfile文件)
$ docker tag 860c279d2fec runoob/centos:dev  | 设置镜像标签

#dockerhub  
$ docker login                              # 登录
$ docker logout                             # 登出
$ docker search ubuntu                      # 搜索
$ docker tag ubuntu:18.04 Zero/ubuntu:18.04 #
$ docker image ls                           #
$ docker push Zero/ubuntu:18.04             # 推送
$ docker search username/ubuntu             # 查询(测试)
```


## 示例

```bash
$ docker search mysql
$ docker pull mysql:latest
$ docker images
$ docker run -itd --name mysql-test -p 3306:3306 -e MYSQL_ROOT_PASSWORD=iscs200 mysql
#-p 3306:3306 ：映射容器服务的 3306 端口到宿主机的 3306 端口，外部主机可以直接通过 宿主机ip:3306 访问到 MySQL 的服务
#MYSQL_ROOT_PASSWORD=123456：设置 MySQL 服务 root 用户的密码。 
$ docker run -itd --name mysql-dev -p 3306:3306 -e MYSQL_ROOT_PASSWORD=iscs200 mysql:5.6.20
$ docker ps   #查看是否安装(获得容器id)
$ docker stop   <容器 ID>  
```

## 容器基本操作
```bash
$ docker run -it ubuntu /bin/bash                     | 启动容器,命令行模式进入
$ docker run -d -P training/webapp python app.py      | -P 随机端口, -p指定端口
$ docker run -itd --name ubuntu-test ubuntu /bin/bash | 启动容器,后台运行
$ docker attach 1e560fca3906                          | 进入后台运行容器(容器退出,容器的停止)
$ docker exec -it 243c32535da7 /bin/bash              | 进入后台运行容器(容器退出,容器不停止)
$ docker start  <容器 ID>                             | 启动
$ docker stop   <容器 ID>                             | 停止
$ docker rm -f 1e560fca3906                           | 删除容器( 删除容器时，容器必须是停止状态，否则会报错误 )
$ docker restart   <容器 ID>                          | 重启
$ docker logs  <容器 ID>                              | 在container外面查看它的输出
$ docker attach  <容器 ID>                            | 连接上容器实时查看
```

## 容器清理操作
```
$ docker container prune                                   # 清理掉所有处于终止状态的容器
$ docker volume create exeed-db                            # 命令创建名称为exeed-db的volume
$ docker ps                                                # 查看运行容器
$ docker ps -a                                             # 查看所有容器
$ docker ps -n 5                                           # 看一下最新前5个
$ docker ps -l                                             # 查询最后一次创建的容器：
$ docker exec -it d27bd3008ad9 /bin/bash                   # 进入容器(d27bd3008ad9)
$ docker stop $(docker ps -q)                              # 停用全部运行中的容器
$ docker rm $(docker ps -aq)                               # 删除全部容器
$ docker stop $(docker ps -q) & docker rm $(docker ps -aq) # 停止并删除容器
$ docker export 1e560fca3906 > ubuntu.tar  | 导出容器快照
$ cat docker/ubuntu.tar | docker import - test/ubuntu:v1   # 导入容器快照 (快照ubuntu.tar -> test/ubuntu:v1镜像)
$ docker import http://example.com/exampleimage.tgz example/imagerepo
```





```bash 
$  docker tag toneloc01/oracle-xe-11g xopens
$  docker run txopens
```


## 查看网络  
```bash
$docker network ls
$ docker run -itd --name test1 --network bridge --ip 192.168.44.233 xopens /bin/bash
```


## docker compose
## dockerfile 
```bash 
$ mkdir Dockerfile 
$ cd Dockerfile 
$ vi Dockerfile 

#创建3层
FROM centos
RUN yum install wget 
RUN wget -O redis.tar.gz "http://download.reidis.io/releases/redis-5.0.3.tar.gz"
RUN tar -xvf redis.tar.gz 

#创建1层 
FROM centos
RUN yum install wget  \
    &&  wget -O redis.tar.gz "http://download.reidis.io/releases/redis-5.0.3.tar.gz"\
    && tar -xvf redis.tar.gz 

$ docker build -t centos:v2 . | 构建镜像
#指令说明                     |
COPY testfile.txt /mydir/     |
ADD                           |
CMD                           |
ENTRYPOINT                    |
ENV                           | 设置环境变量
ARG                           | 设置环境变量(dockerfile内有效)
VOLUME                        |
EXPOSE                        |
WORKDIR                       | 指定工作目录
USER                          | 指定用户和用户组
HEALTHCHECK                   |
ONBUILD                       | 延时执行

```


## 示例 
### 运行一个web应用
```bash 
$ docker pull training/webapp  # 载入镜像
$ docker run -d -P training/webapp python app.py
        -d:让容器在后台运行。
        -P:将容器内部使用的网络端口随机映射到我们使用的主机上
$ docker ps 
    这时我们可以通过浏览器访问WEB应用  http://192.168.44.128:32768/
$ docker run -d -p 5000:5000 training/webapp python app.py  #自定义映射端口
$ docker port bf08b7f2cd89  | 查看端口映射
$ docker port wizardly_chandrasekhar  | 查看端口映射
$ docker logs -f bf08b7f2cd89 | 查看日志输出
$ docker top wizardly_chandrasekhar  | 查看容器进程
$ docker stop wizardly_chandrasekhar    | 停止并删除容器
$ docker start wizardly_chandrasekhar  | 启动
$ docker restart  wizardly_chandrasekhar | 重启
$ docker rm wizardly_chandrasekhar  | 移除
```
### 安装oracle 
```bash 
$docker pull toneloc01/oracle-xe-11g
$docker run toneloc01/oracle-xe-11g
$docker ps -a
CONTAINER ID        IMAGE                     COMMAND             CREATED              STATUS                         PORTS                NAMES
6b005c3737f7        toneloc01/oracle-xe-11g   "/entrypoint.sh "   About a minute ago   Up About a minute              1521/tcp, 8080/tcp   eager_hertz
2f5cb4235863        toneloc01/oracle-xe-11g   "/entrypoint.sh "   7 minutes ago        Exited (0) 3 minutes ago                            clever_pascal
$ docker exec -it 6b005c3737f7 /bin/bash
root@6b005c3737f7:/# su oracle
oracle@6b005c3737f7:/$ cd /u01/app/oracle/product/11.2.0/xe/bin
SQL>
```

wnameless/oracle-xe-11g
toneloc01/oracle-xe-11g




## 开发环境配制

https://www.jb51.net/article/195427.htm



```cmd
$ docker --version
$ docker-compose --version
$ docker-machine --version
$ docker run hello-world     #来测试从Docker Hub拉一个图像并启动一个容器
$ docker run -it ubuntu bash #运行Ubuntu容器
```