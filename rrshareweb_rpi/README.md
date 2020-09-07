# rrshare
rrshare for docker（基于arm64v8/ubuntu+最新版人人影视客户端）

### 人人影视客户端ARM64位Docker版支持（树莓派，NanoPi等一切64位系统）官方最新系统

```
docker run -dit -p 3001:3001 -v /opt/rrdata:/opt/work/rrshareweb/data --name rrys nathandai1998/rrshare_arm64
```
访问http://ip:3001 打开后台 解锁密码默认为123456，可在设置里面修改
参数说明：
- -p　3001端口可自定义，比如想改成80端口，可以改为-p 80:3001
- -v　用于宿主机挂载下载后文件目录，可通过根目录/opt/rrdata查看

### 关于停止、启动、删除
```
docker stop rrys     # 停止运行人人影视
docker start rrys    # 启动
docker rm rrys       # 删除容器
```