# 中文版-Transmission

[![Docker Pulls](https://img.shields.io/docker/pulls/oldiy/transmission-twc.svg)][dockerhub] 

[dockerhub]: https://hub.docker.com/r/oldiy/transmission-twc

---

执行命令：

---

```
docker create --name=transmission \
-v <path to data>:/config \
-v <path to downloads>:/downloads \
-v <path to watch folder>:/watch \
-e PGID=<gid> -e PUID=<uid> \
-e TZ=<timezone> \
-p 9091:9091 -p 45555:45555 \
-p 45555:45555/udp \
oldiy/transmission-twc
```

---

+ 觉得不错，请点上方 ] ★ [ 

+ [ [ - 群晖图文视频安装教程 - ](https://odcn.top/2018/11/27/1669/) ]

+ [ [ - Blog - ](https://odcn.top) ]

---

## 参数

* `-p 9091`  - 访问端口
* `-p 45555` - 通讯端口
* `-v /config` - 配置文件和日志目录
* `-v /downloads` - 下载目录
* `-v /watch` - 监视torrent的文件夹
* `-e PGID`  GroupID 
* `-e PUID`  UserID
* `-e TZ` 时区设置

### PGID、PUID用法

有时，当使用数据卷（`-v`参数）挂载目录时，宿主机和容器之间可能会出现权限问题。可以通过指定用户“PUID”和组“PGID”来避免此问题。确保宿主机目录是由您指定的同一用户拥有。

可以使用 `cat /etc/passwd` 命令查看PGID和PUID