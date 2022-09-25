# 构建
```
docker buildx build --platform linux/arm64,linux/amd64 -t lihaixin/speedtest https://ghproxy.com/https://github.com/lihaixin/speedtest-docker.git  --push
```
## 用法：

### CLI

```
docker run -itd --name speedtest --hostname speedtest --restart=always -p 0.0.0.0:80:80 lihaixin/speedtest
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

```
