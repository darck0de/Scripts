# Run openvpn inside docker container

## Step 1 - Run docker container
`sudo docker run -it -v $HOME:/home --cap-add=NET_ADMIN alpine `

## Step 2 - Run Script from my gtihub
`cd /home && wget https://raw.githubusercontent.com/darck0de/Scripts/master/openvpn.sh && cat openvpn.sh | sh`

## Step 3 - Install openvpn client
`apk add openvpn`

## Step 4 - Copy your openvpn config file to host's home directory then Go to home directory of container
` cd \home `

## Step 5 - Start openvpn client
` openvpn <openvpnconfig.ovpn>
