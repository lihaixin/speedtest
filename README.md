# 构建
```
docker buildx build --platform linux/arm64,linux/amd64 -t lihaixin/speedtest https://ghproxy.com/https://github.com/lihaixin/speedtest-docker.git  --push
```
# speedtest

一款HTML5在线测试网速的小工具,居于Alpine构建的镜像，可测试上传速度、下载速度、访问延迟、延迟抖动

## 用法：

### CLI

```
docker run -d --name speedtest --hostname speedtest --restart=always -p 0.0.0.0:80:80 lihaixin/speedtest
```

### docker-compose.yml

```
version: "3.7"
services:
  speedtest:
    image: lihaixin/speedtest
    container_name: speedtest
    hostname: speedtest
    restart: unless-stopped
    network_mode: "bridge"
    logging:
      driver: json-file
      options:
        max-size: 1m
    ports:
      - "80:80"

```
## 终端截图

```
                              __          __         _                                   
                               \ \        / /        | |                                  
                                \ \  /\  / /    ___  | |   ___    ___    _ __ ___     ___ 
                                 \ \/  \/ /    / _ \ | |  / __|  / _ \  | '_ ` _ \   / _ \
                                  \  /\  /    |  __/ | | | (__  | (_) | | | | | | | |  __/
                                   \/  \/      \___| |_|  \___|  \___/  |_| |_| |_|  \___|
                                                                                          
                                                                                          
                                                               _   _                  _   
                                                              | | | |                | |  
                               ___   _ __     ___    ___    __| | | |_    ___   ___  | |_ 
                              / __| | '_ \   / _ \  / _ \  / _` | | __|  / _ \ / __| | __|
                              \__ \ | |_) | |  __/ |  __/ | (_| | | |_  |  __/ \__ \ | |_ 
                              |___/ | .__/   \___|  \___|  \__,_|  \__|  \___| |___/  \__|
                                    | |                                                   
                                    |_|                                                   
 # ------------------------------------------------------------------------------------------------ #
 # 在线测试网速的小工具,部署到海外机房,特别适合需要经常测试访问外网的用户 
 # SPEEDTEST (外网IP) 测速地址: http://*.*.*.*:80 （如更改映射的端口，请使用对应端口替换80）
 # SPEEDTEST (内网IP) 测速地址: http://*.*.*.*:80  （如更改映射的端口，请使用对应端口替换80）
 # 
 # 更多信息访问网页查看： https://hub.docker.com/r/lihaixin/speedtest 
 # ------------------------------------------------------------------------------------------------ #
```
