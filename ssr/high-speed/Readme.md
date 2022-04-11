> 参考

- ss

  https://iyideng.net/black-technology/cgfw/shadowsocks-ss-server-building-and-using-tutorial.html

- xray


  https://iyideng.net/black-technology/cgfw/xray-xtls-one-click-script-building-and-using-tutorial.html
  
  https://github.com/XTLS/Xray-install
  
  https://github.com/kirin10000/Xray-script

  ```shell
  wget https://raw.githubusercontent.com/kirin10000/Xray-script/main/Xray-TLS+Web-setup.sh && chmod +x Xray-TLS+Web-setup.sh && ./Xray-TLS+Web-setup.sh
  ```

- shadowsocks-all.sh


  https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh

  ```shell
  ## install/remove
  ./shadowsocks-all.sh # install
  ./shadowsocks-all.sh uninstall # remove
  ## Stop/Start
  Shadowsocks-Python 版：
  /etc/init.d/shadowsocks-python start | stop | restart | status
  
  ShadowsocksR 版：
  /etc/init.d/shadowsocks-r start | stop | restart | status
  
  Shadowsocks-Go 版：
  /etc/init.d/shadowsocks-go start | stop | restart | status
  
  Shadowsocks-libev 版：
  /etc/init.d/shadowsocks-libev start | stop | restart | status
  
  ## config
  Shadowsocks-Python 版：
  /etc/shadowsocks-python/config.json
  
  ShadowsocksR 版：
  /etc/shadowsocks-r/config.json
  
  Shadowsocks-Go 版：
  /etc/shadowsocks-go/config.json
  
  Shadowsocks-libev 版：
  /etc/shadowsocks-libev/config.json
  ```

- Shadowsocks+WS+TLS+CDN

  https://github.com/M3chD09/shadowsocks-with-v2ray-plugin-install/raw/master/centos-ss-install.sh
  
  https://github.com/M3chD09/shadowsocks-with-v2ray-plugin-install/raw/master/ubuntu-ss-install.sh

  https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh # bbr

  ```shell
  # service 
  systemctl status shadowsocks #运行状态
  systemctl start shadowsocks #启动
  systemctl stop shadowsocks #停止
  # bbr 加速
  cd /usr/src && wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh
  
  ```

- h5ai

  ```bash
  docker pull ilemonrain/h5ai:full
  docker run itd -p [80]:80 -v [$PWD]:/h5ai --name h5ai --restart always ilemonrain/h5ai:[lite/full]
  ```

  
