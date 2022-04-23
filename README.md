##用法：

```
docker run -d --name speedtest --restart=always -p 0.0.0.0:80:80 lihaixin/speedtest
docker buildx build --platform linux/amd64 -t lihaixin/speedtest https://github.com/lihaixin/speedtest-docker.git  --push

docker run [-t/-d] -p [6688]:80 ilemonrain/html5-speedtest:latest
``
