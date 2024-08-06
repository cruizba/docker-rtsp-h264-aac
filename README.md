# docker-rtsp-h264-aac
A simple docker compose to reencode RTSP streams to H264 and AAC using mediamtx

## Why

Sometimes IP Cameras comes with weird codecs that are not supported by some legacy software which can just play H264 and AAC. This project aims to reencode RTSP streams to H264 and AAC using mediamtx in a simple way. Ffmpeg is a great tool to do this, and it is embedded in mediamtx official docker images, so I decided to do this for quick and easy use.

It is specially useful also for Kurento Media Server, which does not support some codecs.

## How to use

1. Clone this repository
2. `cd docker-rtsp-h264-aac`
3. Go to `.env` and define your RTSP_URL with the RTSP URL of your camera. For example: `RTSP_URL=rtsp://<yourcamera>:554/`
4. Run `docker-compose up`

## Check if it's working

```
ffplay rtsp://admin:password@localhost:8555/rtsp
```

## Change rtsp basic auth

Modify the `mediamtx.yml` file here:

https://github.com/cruizba/docker-rtsp-h264-aac/blob/756e50da9f87a76ce85997a8455b70d64d1fa40e/mediamtx.yml#L58-L59

## Modify ffmpeg command

The ffmpeg command is available in the `docker-compose.yml`:

https://github.com/cruizba/docker-rtsp-h264-aac/blob/25a446cfc3f9f19a5f082c31e7b9d982c0162379/docker-compose.yml#L11-L14

