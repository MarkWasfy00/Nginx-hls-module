FROM ubuntu:24.04

RUN apt update
RUN apt install -y ffmpeg

WORKDIR /media

ENTRYPOINT ffmpeg -rtsp_transport tcp -i ${RTSP_URL} -c:v libx264 -preset veryfast -tune zerolatency -vf scale=1920:1080 -b:v 3000k -maxrate 3000k -bufsize 6000k -g 60 -c:a aac -b:a 128k -f flv rtmp://a.rtmp.youtube.com/live2/${YOUTUBE_STREAM_KEY}