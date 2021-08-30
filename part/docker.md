# docker command
docker, nvidia-docker command

## index
- [docker save](#docker-save)
- [docker commit](#docker-commit)
- [docker copy](#docker-copy)
- [docker run example](#docker-run-example)

### docker save
```
docker save -o [name.tar.gz] [images:tag]
```

### docker commit 
```
docker commit -m "[message]" [container_name] [images:tag]
```

### docker copy
```
# container -> local
docker cp [container name]:[dir] [local_dir]
# local -> container
docker cp [local_dir] [container name]:[dir] 
```

### docker run example
```
docker run --name [container name] \
-h [hostname] \
-v [external dir]:[container dir] \
-e LC_ALL=ko_KR.UTF-8 \
-p [external port]:[internal port]
--gpus '"device=1"' \
-tid [images:tag]

```
