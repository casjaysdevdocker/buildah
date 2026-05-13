## 👋 Welcome to buildah 🚀  

buildah README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update buildah
```
  
## Install and run container
  
```shell
dockerHome="/var/lib/srv/$USER/docker/casjaysdevdocker/buildah/buildah/latest/rootfs"
mkdir -p "/var/lib/srv/$USER/docker/buildah/rootfs"
git clone "https://github.com/dockermgr/buildah" "$HOME/.local/share/CasjaysDev/dockermgr/buildah"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/buildah/rootfs/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-buildah-latest \
--hostname buildah \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/buildah:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/buildah
    container_name: casjaysdevdocker-buildah
    environment:
      - TZ=America/New_York
      - HOSTNAME=buildah
    volumes:
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/buildah/buildah/latest/rootfs/data:/data:z"
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/buildah/buildah/latest/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/buildah
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/buildah" "$HOME/Projects/github/casjaysdevdocker/buildah"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/buildah"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
