# docker-rtsp-reencoder
A simple docker compose to reencode RTSP streams to H264 and AAC using mediamtx

# Why

Sometimes IP Cameras comes with weird codecs that are not supported by some legacy software which can just play H264 and AAC. This project aims to reencode RTSP streams to H264 and AAC using mediamtx in a simple way. Ffmpeg is a great tool to do this, and it is embedded in mediamtx official docker images, so I decided to do this for quick and easy use.

# How to use

1. Clone this repository
2. Go to `.env` and define your RTSP_URL with the RTSP URL of your camera. For example: `RTSP_URL=rtsp://<yourcamera>:554/`
3. Run `docker-compose up`

# Check if it's working

The docker-compose will expose a new RTSP endpoint at `rtsp://localhost:8555/rtsp` which you can use to check if the reencoding is working. You can use VLC to check it. Just open VLC, go to `Media > Open Network Stream` and type `rtsp://localhost:8555/rtsp` and click `Play`.

The stream should be reencoded to H264 and AAC.
