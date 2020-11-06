# ffmpeg常用命令

## 视频

### flv -> mp4

```shell
ffmpeg -i in.flv -vcodec copy -acodec copy output.mp4
```



### ts -> mp4

```shell
ffmpeg -y -i in.ts -vcodec copy -acodec copy -vbsf h264_mp4toannexb out.mp4
```



### mov -> mp4

```shell
ffmpeg -i in.mov -vcodec copy -acodec copy out.mp4
```



### 视频去掉声音

```shell
ffmpeg -i in.mp4 -vcodec copy -an out.mp4
```



### 提取视频音频

```shell
ffmpeg -i in.mp4 -vn -codec copy out.m4a
```



### 视频切片

```shell
ffmpeg -ss 00:04:46 -t 00:00:32 -i in.mp4 -vcodec copy -acodec copy output.mp4
```



## 音频

### mp3 -> wav

```shell
ffmpeg -i in.mp3 -acodec pcm_s16le -ac 2 -ar 44100 output.wav
```



### m4a -> wav

```shell
ffmpeg -i in.m4a -acodec pcm_s16le -ac 2 -ar 44100 in.wav
```



### wav -> mp3

```shell
ffmpeg -i "in.wav" -b:a 64k -acodec mp3 -ar 44100 -ac 1 "out.mp3"
```



### 音频拼接（mp3）

```shell
ffmpeg -i "concat:01.mp3|02.mp3" -acodec copy output.mp3
```



## 其他

### 保留原声合并音视频

```shell
ffmpeg -i bgm.mp3 -i in.mp4 -filter_complex amix=inputs=2:duration=first:dropout_transition=2 output.mp4
```



### 无原声合并音视频

```shell
ffmpeg -i bgm.mp3 -i in.mp4 output.mp4
```



