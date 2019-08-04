# FFmpeg

## 常用语句

* 截取视频

  ```text
  ffmpeg -ss 01:00:00 -t 00:01:00 -i in.mkv -vcodec copy -acodec copy out.mkv
  ```

  `-ss`后为开始的时间  
  `-t`后为截取的时长

* 转视频格式

  ```text
  ffmpeg -i in.mkv -c:v copy -c:a copy out.mp4
  ```

* [增大容器封装封装队列大小](https://blog.csdn.net/noahsun1024/article/details/80875460)

  ```text
  -max_muxing_queue_size 1024
  ```

* [裁剪视频](https://amoskong.wordpress.com/2014/09/29/%E8%BD%AC-%E4%BD%BF%E7%94%A8-ffmpeg-%E7%BC%A9%E6%94%BE%E3%80%81%E8%A3%81%E5%89%AA%E3%80%81%E5%89%AA%E8%BE%91%E8%A7%86%E9%A2%91/)

    ```
    # ffmpeg -i in.mkv -vf crop=width:height:x:y out.mkv
    ffmpeg -i in.mkv -vf crop=400:400:0:0 out.mkv
    ```
    `x`,`y` 是相对于视频左上角的像素坐标，裁剪的七点
    `width`,`height` 表示要裁剪的像素尺寸

* [缩放视频](https://amoskong.wordpress.com/2014/09/29/%E8%BD%AC-%E4%BD%BF%E7%94%A8-ffmpeg-%E7%BC%A9%E6%94%BE%E3%80%81%E8%A3%81%E5%89%AA%E3%80%81%E5%89%AA%E8%BE%91%E8%A7%86%E9%A2%91/)

    ```
    # ffmpeg -i in.mkv -vf scale=width:height out.mkv
    ffmpeg -i in.mkv -vf scale=1280:720 out.mkv
    ffmpeg -i in.mkv -vf scale=1280:720 out.mkv
    ```
    `width`,`height` 缩放后的高和宽，其中一项填为`-1`会保持比例缩放

    可以和裁剪一起使用：
    ```
    ffmpeg -i in.mkv -strict -2 -vf scale=853:480,crop=480:480:186:0 out.mkv
    ```

* [合并视频](https://www.jianshu.com/p/a9bccc12229b)
    有多种方法：
    1. FFmpeg concat 分离器  
        步骤：
        1. 将要合并的视频写到文件`filelise.txt`中

            ```
            file 'in0.mkv'
            file 'in1.mkv'
            file 'in2.mkv'
            ```
        1. 
            ```
            ffmpeg -f concat -i filelist.txt -c copy out.mkv
            ```
    
    1. 使用 FFmpeg concat 过滤器重新编码（有损）
    ```
    ffmpeg -i .\out1.mkv -i .\out.mp4 -i .\out.mkv -filter_complex '[0:0] [0:1] [1:0] [1:1] [2:0] [2:1] concat=n=3:v=1:a=1 [v] [a]' -map '[v]' -map '[a]' connectWithContact.mkv
    ```

* [内嵌字幕](https://www.cnblogs.com/tocy/p/ffmpeg-basic-learning-3.html#subtitles-video-filter%E5%86%85%E5%B5%8C%E5%AD%97%E5%B9%95%E6%B5%81)
    
    ```
    ffmpeg -i in.mkv -vf subtitles=titles.srt out.mkv
    ```

## Refs

[FFmpeg](https://ffmpeg.org/)

