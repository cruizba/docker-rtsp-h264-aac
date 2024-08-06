# docker-rtsp-h264-aac

A straightforward Docker Compose setup to re-encode RTSP streams to H264 and AAC using mediamtx.

## Purpose

Many IP cameras use codecs that are incompatible with certain legacy software that only supports H264 and AAC. This project re-encodes RTSP streams to H264 and AAC using ffmpeg for transcoding and mediamtx to present a new RTSP server. Ffmpeg and mediamtx are excellent tools for this task, prompting the creation of this easily modifiable Docker Compose setup.

## Usage

1. Clone this repository.
2. Navigate to the project directory: `cd docker-rtsp-h264-aac`
3. Edit the `.env` file to set your RTSP_URL with the camera's RTSP URL. For example: `RTSP_URL=rtsp://<yourcamera>:554/`
4. Run `docker-compose up`

## Verify Operation

Check if the stream is working by running:

```sh
ffplay rtsp://admin:password@localhost:8555/rtsp
```

## Change RTSP Basic Auth

To modify the RTSP basic authentication settings, edit the `mediamtx.yml` file at the following lines:

[mediamtx.yml#L58-L59](https://github.com/cruizba/docker-rtsp-h264-aac/blob/756e50da9f87a76ce85997a8455b70d64d1fa40e/mediamtx.yml#L58-L59)

## Modify ffmpeg Command

The ffmpeg command can be adjusted in the `docker-compose.yml` file at the following lines:

[docker-compose.yml#L11-L14](https://github.com/cruizba/docker-rtsp-h264-aac/blob/25a446cfc3f9f19a5f082c31e7b9d982c0162379/docker-compose.yml#L11-L14)
