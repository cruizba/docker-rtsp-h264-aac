# docker-rtsp-reencoder
A simple docker compose to reencode RTSP streams to H264 and AAC using mediamtx

# Why

Sometimes IP Cameras comes with weird codecs that are not supported by some legacy software which can just play H264 and AAC. This project aims to reencode RTSP streams to H264 and AAC using mediamtx in a simple way. Ffmpeg is a great tool to do this, and it is embedded in mediamtx official docker images, so I decided to do this for quick and easy use.

It is specially useful also for Kurento Media Server, which does not support some codecs.

# How to use

1. Clone this repository
2. Go to `.env` and define your RTSP_URL with the RTSP URL of your camera. For example: `RTSP_URL=rtsp://<yourcamera>:554/`
3. Run `docker-compose up`

# Check if it's working

```
ffplay rtsp://admin:password@localhost:8555/rtsp
```
