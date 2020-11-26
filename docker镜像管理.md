### docker 镜像管理

#### 1.镜像是什么

- 一个分层存储的文件
- 一个软件环境
- 一个镜像可以创建N个容器
- 一种标准化的交付
- 一个不包含Linux 而又精简的Linux操作系统

#### 2.镜像从哪里来?

- 镜像仓库 (docker hub)

#### 3.创建一个Nginx容器

````shell
# 不指定版本号将使用最新版 latest
docker run -d -p 8080:80 nginx

# docker 查看镜像
docker ps

# docker 查看log 
docker logs <镜像id>
````

 #### 4.镜像加速器

````shell
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://r6relysg.mirror.aliyuncs.com"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
````

#### 5.镜像与容器联系

镜像: 类似于虚拟机镜像,一个只读模板

容器:通过镜像创建的实例
https://github.com/zengana/docker/blob/main/photo/container.png


````shell
# docker 存储位置
/var/lib/docker
# 查看容器详细信息
docker inspect <容器id>
````

