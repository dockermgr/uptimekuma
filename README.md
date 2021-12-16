# Welcome to dockermgr uptimekuma installer 👋
  
## a self-hosted monitoring tool like "Uptime Robot"  
  
### Requires scripts to be installed

```shell
 sudo bash -c "$(curl -LSs <https://github.com/dockermgr/installer/raw/main/install.sh>)"
 dockermgr --config && dockermgr install scripts  
```

#### Automatic install/update  

```shell
dockermgr install uptimekuma
```


#### Manual install

```shell
git clone https://github.com/dockermgr/uptimekuma "$HOME/.local/share/CasjaysDev/dockermgr/uptimekuma"
bash -c "$HOME/.local/share/CasjaysDev/dockermgr/uptimekuma/install.sh"
```
  
#### Just run it

```shell
mkdir -p "$HOME/.local/share/srv/docker/uptimekuma/"

git clone <https://github.com/dockermgr/uptimekuma> "$HOME/.local/share/CasjaysDev/dockermgr/uptimekuma"

cp -Rfva "$HOME/.local/share/srv/docker/uptimekuma/dataDir/." "$HOME/.local/share/srv/docker/uptimekuma/"

sudo docker run -d \
--name="uptimekuma" \
--hostname "uptimekuma" \
--restart=always \
--privileged \
-e TZ="${TZ:-${TIMEZONE:-America/New_York}}" \
-v "$HOME/.local/share/srv/docker/uptimekuma/files/data":/app/data:z \
-v "$HOME/.local/share/srv/docker/uptimekuma/files/config":/app/config:z \
-p 3001:3001 \
louislam/uptime-kuma 1>/dev/null
```

## Author  

👤 **Jason Hempstead**  
