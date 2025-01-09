原镜像 README 参考 https://github.com/belane/docker-bloodhound

将原本的 bloodhound 从 4.20 升到了 4.31

其他无变化

使用方法 Clone 下来 `docker build .`

构建好镜像后

```shell
xhost +local:$(id -nu)
docker run -it --shm-size=1g \
  -p 7474:7474 \
  -e DISPLAY=unix$DISPLAY \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  --device=/dev/dri:/dev/dri \
  -v $(pwd)/bh-data:/data \
  --name bloodhound <image id>
```
启动

在 Kali 2024.4 中运行成功
