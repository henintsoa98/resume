# youtube.md
## Install yt-dlp
### linux x86_64
```bash
wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp_linux
chmod +x yt-dlp_linux
sudo cp yt-dlp_linux /usr/local/bin/yt-dlp
```
### linux arm64
```bash
wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp_linux
chmod +x yt-dlp_linux
sudo cp yt-dlp_linux /usr/local/bin/yt-dlp
```
### linux arm32
```bash
wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp_linux_armv7l
chmod +x yt-dlp_linux_armv7l
sudo cp yt-dlp_linux_armv7l /usr/local/bin/yt-dlp
```
## Download playlist
```bash
yt-dlp -o './%(playlist)s/%(playlist_index)02d - %(title)s.%(ext)s' LINK
```
## Download video
```bash
yt-dlp LINK
```
