# ssh-ngrok.md
## Install ngrok
### amd64
```bash
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz
sudo tar -xvzf ngrok-v3-stable-linux-amd64.tgz -C /usr/local/bin
```
### arm64
```bash
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-arm64.tgz
sudo tar -xvzf ngrok-v3-stable-linux-arm64.tgz -C /usr/local/bin
```
### arm32
```bash
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-arm.tgz
sudo tar -xvzf ngrok-v3-stable-linux-arm.tgz -C /usr/local/bin
```
## Configure
Login  [here](https://dashboard.ngrok.com/signup) and visit [ngrok setup page](https://dashboard.ngrok.com/get-started/setup/linux) to get token
```bash
ngrok config add-authtoken [token]
```
## Expose ssh over internet (I use on Colab and play-with-docker)
```bash
ngrok tcp 22
# see Forwarding : link an port to connect over internet
```
## Expose webserver
```bash
ngrok http 80
# see
```
