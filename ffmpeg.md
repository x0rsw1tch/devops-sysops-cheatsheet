# FFMpeg Cheatsheet

## Convert to mp4/x264/AAC
```
ffmpeg -i INFILE -c:v libx264 -c:a aac OUTFILE
```


## Convert to mp4/x264/AAC audio, with specified bitrates
```
ffmpeg -i INFILE -c:v libx264 -c:a aac -b:v VIDEO_BIRATE -b:a AUDIO_BITRATE OUTFILE
```


## Slice source video from timestamps
> Ref: [FFMpeg Wiki1](https://trac.ffmpeg.org/wiki/Seeking)
```
ffmpeg -ss 00:00:00 -to 00:00:00 -c copy -i INFILE OUTFILE
```


## Capture video from capture device
```
ffmpeg -f dshow -i video="CAPTURE_DEVICE":audio="AUDIO_DEVICE" -video_size 1280x720 -pixel_format yuv420p -framerate 30 -vcodec mjpeg -c:v libx264 -qp 0 OUTFILE
```


## Stream Local MP4 File to YT, no encoding
```
ffmpeg -re -i INFILE -c copy -f flv rtmp://a.rtmp.youtube.com/live2/YTKEY
```


## Encode and stream Local File to YT
```
ffmpeg -re -i INFILE -c:v libx264 -s 1920x1080 -preset veryfast -maxrate 8000k -bufsize 40000k -pix_fmt yuv420p -g 50 -c:a aac -b:a 160k -ac 2 -ar 44100 -f flv rtmp://a.rtmp.youtube.com/live2/YTKEY 
```


## Capture desktop
```
ffmpeg -f gdigrab -i desktop -show_region 1
```
