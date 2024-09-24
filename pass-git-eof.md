## create a workspace
Use the directory as your choice (here ~/DOCKER)
```bash
mkdir -p ~/DOCKER/data
```

## setup the cloud-shell
```bash
cd ~/DOCKER
echo "
services:
  gcloud:
    image: "gcr.io/google.com/cloudsdktool/google-cloud-cli"
    container_name: "gcloud"
    command: "sleep infinity"
    privileged: true
    volumes:
      - "./data:/data/"
" > compose.yaml
```

## Launch the docker
### First time only (this is the creation of the container)
```bash
cd ~/DOCKER
docker compose up -d
```

### After rebooting the PC, You only need to start container with
```bash
docker start gcloud
``` 

## Enter into the container
```bash
docker exec -ti gcloud bash
```

## install requirement into container (one time only)
```bash
apt update
apt install sshfs
```

## Login with google accout (only first time after creating the container, not need after rebooting pc)
This give you a link and accept it into your navigator, and it give you a code to paste in next prompt
```bash
gcloud auth login
```

## entering into google cloud
Accept with no password (if you like, not tested for me, for simplicity)
```bash
gcloud cloud-shell ssh
## here you can download anything into ~, you can compress it to get faster upload to your computer, eg :
## git clone https://github.com/henintsoa98/resume
## tar cJf resume.tar.xz resume
```

## MOUNT CLOUD SHELL to CONTAINER
Enter into the container into new tab :
```bash
docker exec -ti gcloud bash
```
### mount home(cloud-shell) to /media(container)
```bash
eval `gcloud cloud-shell get-mount-command /media`
```
now your cloud-shell is mounted into media of container
### COPY downloaded file or folder to MACHINE LOCAL (IT USE INTERNET DATA )
```bash
cp /media/resume.tar.xz /data
```
now you can see file into ~/DOCKER/data
### change privilege of downloader file on MACHINE LOCAL
```bash
cd ~/DOCKER/data
sudo chown -R 1000:1000 * 
```
