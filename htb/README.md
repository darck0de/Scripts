# Kali docker for Hackthebox

## Start Docker Container
```docker run -it --name kali --sysctl net.ipv6.conf.all.disable_ipv6=0 --cap-add=NET_ADMIN --device /dev/net/tun -h kali -v $HOME/Downloads:/home/kali/ darkc0de/kali:latest```

## HTB VPN Connect (change htb.ovpn with your filename which is in your host home directory)
```cd /home/kali && openvpn htb.ovpn```

## Detach container - Once vpn is connected you can hit below keystrokes to detach the container
Ctrl-p + Ctrl-q

## Commands from Host terminal
```docker exec -it kali /etc/init.d/ssh start```

## Commands from Host terminal (SSH tunnel , use kali as password)
```ssh -D 8123 -f -C -q -N kali@172.17.0.2```

## Setup Foxyproxy settings to SOCKS5
- Enable SOCKS Proxy checkbox, SOCKS v5 , Port 8123
