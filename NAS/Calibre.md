## Update  Calibre
```shell
alias runlike="docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro assaflavie/runlike"

runlike containerID
```

```shell
docker run -d \
--name=calibre \
--hostname=calibre \
--env=PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin \
--env=HOME=/config \
--env=LANGUAGE=en_US.UTF-8 \
--env=LANG=en_US.UTF-8 \
--env=TERM=xterm \
--env=NVIDIA_DRIVER_CAPABILITIES=compute,video,utility \
--env=CUSTOM_PORT=8080 \
--env=GUIAUTOSTART=true \
--env=PGID=100 \
--env=PUID=1026 \
--env=HTTP_PROXY=socks5h://192.168.6.1:1080 \
--env=HTTPS_PROXY=socks5h://192.168.6.1:1080 \
--volume=/volume1/homes/itangbin/Drive/Books:/books:rw \
--volume=/volume1/docker/calibre:/config:rw \
--network=bridge \
-p 8080:8080 \
-p 8081:8081 \
--restart=unless-stopped \
-t linuxserver/calibre:latest
```

```shell
docker run -d \
--name=calibre-ui \
--hostname=calibre-ui \
--mac-address=02:42:ac:11:00:04 \
--env=DOCKER_MODS=linuxserver/calibre-web:calibre \
--env=PGID=100 \
--env=PUID=1026 \
--env=PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin \
--env=HOME=/root --env=LANGUAGE=en_US.UTF-8 \
--env=LANG=en_US.UTF-8 --env=TERM=xterm \
--volume=/volume1/docker/calibre:/config:rw \
--volume=/volume1/homes/itangbin/Drive/Books:/books:rw \
--network=bridge \
-p 8083:8083 \
--restart=no \
-t linuxserver/calibre-web:latest
```