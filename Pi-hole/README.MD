> **What is PI-Hole**

Configure your router’s DHCP options to force clients to use Pi-hole as their DNS server, or manually configure each device​ to use the Pi-hole as their DNS server.

> **Where you can find Pi-Hole document **

##### Reference:
[https://pi-hole.net/](https://pi-hole.net/)

[https://github.com/pi-hole/docker-pi-hole/](https://github.com/pi-hole/docker-pi-hole/)

##### Quick start:
> automatically install script 

```bash
curl -sSL https://install.pi-hole.net | bash
```
> deploy with docker-compose

```bash
cat >docker-compose.yaml<<EOF
version: "3"

# More info at https://github.com/pi-hole/docker-pi-hole/ and https://docs.pi-hole.net/
services:
  pihole:
    container_name: pihole
    image: pihole/pihole:latest
    # For DHCP it is recommended to remove these ports and instead add: network_mode: "host"
    ports:
      - "53:53/tcp"
      - "53:53/udp"
      - "67:67/udp" # Only required if you are using Pi-hole as your DHCP server
      - "80:80/tcp"
    environment:
      TZ: 'America/Chicago'
      # WEBPASSWORD: 'set a secure password here or it will be random'
    # Volumes store your data between container upgrades
    volumes:
      - './etc-pihole:/etc/pihole'
      - './etc-dnsmasq.d:/etc/dnsmasq.d'    
    #   https://github.com/pi-hole/docker-pi-hole#note-on-capabilities
    cap_add:
      - NET_ADMIN # Recommended but not required (DHCP needs NET_ADMIN)      
    restart: unless-stopped
EOF
### 
  docker-compose up -d
```
