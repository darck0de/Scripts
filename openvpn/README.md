# Run openvpn inside docker container

## Step 1 - Run docker container
`sudo docker run -it --name openvpn -v $HOME:/home --cap-add=NET_ADMIN darkc0de/alpine:latest`

## Step 2 - Run Script to setup tun device
`cat ~/openvpn.sh | sh`

## Step 4 - Copy your openvpn config file to host's home directory then Start openvpn 
`openvpn /home/<openvpnconfig.ovpn>`

## Step 5 - Open other terminal and run below command to verify connectivity
`sudo docker exec -ti openvpn sh`

---
### Step 6 - follow below steps when you want to re-connect
`sudo docker start openvpn`

### Follow Step 2 - 5 Again
