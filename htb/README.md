# Kali docker for Hackthebox

```docker run -it --name kali --cap-add=NET_ADMIN -h kali -v $HOME:/home/kali/ darkc0de/kali:latest```

## tun0 device Setup
```cat /root/openvpn.sh | sh```

## HTB VPN Connect (change htb.ovpn with your filename which is in your host home directory)
```cd /home/kali && openvpn htb.ovpn```

## Detach container - Once vpn is connected you can hit below keystrokes to detach the container
Ctrl-p + Ctrl-q

## Commands from Host terminal
```docker exec -it kali /etc/init.d/ssh start```

## Commands from Host terminal (SSH to Kali from Docker using kali user and kali as password)
```ssh kali@172.17.0.2```

## Stop Kali - run from host
```docker stop kali```
