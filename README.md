# THIS IS ALL OF MY SHORT TUTORIAL, READING EACH FILE ON THIS REPO IS SAME TO READ THIS README, JUST USE CTRL-F

# alpine-community.md
## Add community repo
```bash
cat > /etc/apk/repositories << EOF; $(echo)
https://dl-cdn.alpinelinux.org/alpine/v$(cut -d'.' -f1,2 /etc/alpine-release)/main/
https://dl-cdn.alpinelinux.org/alpine/v$(cut -d'.' -f1,2 /etc/alpine-release)/community/
https://dl-cdn.alpinelinux.org/alpine/edge/testing/
EOF
apk update
```

# git-ssh.md
## GENERATE KEY
```bash
ssh-keygen
	# alway press enter
cat ~/.ssh/id_rsa.pub
	# copy all output
```
## KEY TO GITHUB
**go to https://github.com/settings/ssh/new** \
**add title and past the output**
## ADD FILE TO REPO
```
git clone git@github.com:henintsoa98/resume.git
cd resume
	# clone the repo to work
# add some file
git add .
git commit -m "MESSAGE"
git push
```
## LARGE FILE
**using git large file**
```bash
# i was on server so I use this
git config --global user.email "ohenintsoa98@gmail.com"                                                   
git config --global user.name "ONJANIAINA Henintsoa Stephana"
wget https://github.com/git-lfs/git-lfs/releases/download/v3.4.1/git-lfs-linux-amd64-v3.4.1.tar.gz
tar -xzf git-lfs-linux-amd64-v3.4.1.tar.gz
cd git-lfs-3.4.1/
./install.sh # i install on root user but not tested as normal user
cd
git clone git@github.com:henintsoa98/TempFile.git
cd TempFile
	# clone the repo to work
# add some large file file
# cp ../REPO.tar.xz .
git lfs install
git lfs track "*.xz"
git add .gitattributes
git add REPO.tar.xz
git commit -m "this commit contain git clone oh some srslte docker 06/02/24"
git push
```

# link.md
[COLAB FOR DRIVE AND SSH](https://colab.research.google.com/drive/1k_J7s0loXK80UkPI-mO_jnscSoJiaPc4)

# samsung-bootloader.md
1. Automatic date and time
2. Enable mode developer
3. developer
   - disable auto update system
4. Software update
   - disable auto download over wifi
5. Check update
6. Reboot
6. developer
   - unlock oem

# snap-unupdate.md
## disable snap update
```bash
snap refresh --hold
```
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

# tmate.md
## Share terminal into ssh headless
```bash
tmate -S /tmp/tmate.sock new-session -d
tmate -S /tmp/tmate.sock wait tmate-ready
tmate -S /tmp/tmate.sock display -p "#{tmate_ssh}"
```

# youtube.md
## Install yt-dlp
### linux x86_64
```bash
wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp_linux
chmod +x yt-dlp_linux
sudo cp yt-dlp_linux /usr/local/bin/yt-dlp
alias yt-dlpp="yt-dlp -o './%(playlist)s/%(playlist_index)02d - %(title)s.%(ext)s'"
```
### linux arm64
```bash
wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp_linux_aarch64 
chmod +x yt-dlp_linux
sudo cp yt-dlp_linux /usr/local/bin/yt-dlp
alias yt-dlpp="yt-dlp -o './%(playlist)s/%(playlist_index)02d - %(title)s.%(ext)s'"
```
### linux arm32
```bash
wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp_linux_armv7l
chmod +x yt-dlp_linux_armv7l
sudo cp yt-dlp_linux_armv7l /usr/local/bin/yt-dlp
alias yt-dlpp="yt-dlp -o './%(playlist)s/%(playlist_index)02d - %(title)s.%(ext)s'"
```
## Download playlist
```bash
yt-dlp -o './%(playlist)s/%(playlist_index)02d - %(title)s.%(ext)s' LINK
```
## Download video
```bash
yt-dlp LINK
