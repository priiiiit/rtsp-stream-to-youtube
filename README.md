# rtsp-stream-to-youtube
A script that allows to stream RTSP source to Youtube live using FFMPEG.

Usage:
```
./stream-to-youtube.sh <stream key/name>
```

Cheatsheet for used ffmpeg parameters. Needs reformatting and additional information
```
 -f lavfi
 -f anullsrc	-->	null audio source
 -rtsp_transport tcp -i $INPUT
 -tune zerolatency
 -vcodec libx264 ---> Seems that mpeg4 actually works better
 -pix_fmt +	 --->  If pix_fmt is a single +, ffmpeg selects the same pixel format as the input (or graph output) and automatic conversions are disabled.
 -c:v copy
 -c:a aac
 -strict experimental 	---> Not needed anymore
 -f flv rtmp://a.rtmp.youtube.com/live2/$1
```
