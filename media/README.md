#### emby和jellyfin媒体服务器安装配置

> *Jellyfin*

Ref:
https://jellyfin.org/downloads/

```
# Ubuntu
sudo apt install apt-transport-https
wget -O - https://repo.jellyfin.org/jellyfin_team.gpg.key | sudo apt-key add -
echo "deb [arch=$( dpkg --print-architecture )] https://repo.jellyfin.org/$( awk -F'=' '/^ID=/{ print $NF }' /etc/os-release ) $( awk -F'=' '/^VERSION_CODENAME=/{ print $NF }' /etc/os-release ) main" | sudo tee /etc/apt/sources.list.d/jellyfin.list
sudo apt update
sudo apt install jellyfin
systemctl start jellyfin.service && systemctl status jellyfin.service 

# Centos
download pkg from https://repo.jellyfin.org/releases/server/centos/stable/
yum install https://repo.jellyfin.org/releases/server/centos/stable/server/jellyfin-server-10.7.7-1.el7.x86_64.rpm
systemctl status emby-server.service && systemctl status emby-server.service
```
Open a web browser to http://localhost:8096

> *Emby*

Ref:
https://emby.media/linux-server.html
https://github.com/MediaBrowser/Emby.Releases/releases
```
# Ubuntu X64
dpkg -i https://github.com/MediaBrowser/Emby.Releases/releases/download/4.7.0.29/emby-server-deb_4.7.0.29_amd64.deb
```
Open a web browser to http://localhost:8096

