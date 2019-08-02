# FFmpeg

## 常用语句

- 截取视频
    ```
    ffmpeg -ss 01:00:00 -t 00:01:00 -i input.mkv -vcodec copy -acodec copy out.mkv
    ```

    `-ss`后为开始的时间  
    `-t`后为截取的时长

- 转视频格式
    ```
    ffmpeg -i input.mkv -c:v copy -c:a copy out.mp4
    ```

## Refs

[FFmpeg](https://ffmpeg.org/)

