# GENERATE KEY
```bash
ssh-keygen
	# alway press enter
cat ~/.ssh/id_rsa.pub
	# copy all output
```

# KEY TO GITHUB
**go to https://github.com/settings/ssh/new** \
**add title and past the output**

# ADD FILE TO REPO
```
git clone git@github.com:henintsoa98/resume.git
cd resume
	# clone the repo to work
# add some file
git add .
git commit -m "MESSAGE"
git push
```
# LARGE FILE
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
