# Video Tools

## Shotcut

[Shotcut is a free, open source, cross-platform video editor](https://www.shotcut.org/)


## ffmpeg

- Lossless FLV to MP4 conversion
    ```
    ffmpeg -i "filename.flv" -vcodec copy -acodec copy "filename.mp4"
    ```
    From https://gist.github.com/ansonparker/1228449



- 75% size in converted mp4
    ```
    ffmpeg -i "./%*.flv" -c:v libx264 -crf 19 -strict experimental "./%*.mp4"
    ```
    From https://gist.github.com/DevEarley/1e1ea5647562b6218694dcc7c55d2900

    Convert all
    ```
    ls|xargs -I {} ffmpeg -i "{}" -c:v libx264 -crf 19 -strict experimental "{}.mp4"
    ```
	

- [batch file - How to convert rmvb to mp4 with same quality by using ffmpeg? - Stack Overflow](https://stackoverflow.com/questions/50132902/how-to-convert-rmvb-to-mp4-with-same-quality-by-using-ffmpeg)
	
	This converts to h264 video and aac audio. These codecs quite common at present.  
    
    ```
	for %%G in (*.rmvb) do ffmpeg -i "%%~G" -c:v h264 -c:a aac "%%~nG.mp4"
    ```

	```
	ffmpeg -i "abc.rmvb" -c:v h264 -c:a aac "abc.mp4"
    ```
	

- Simply convert	
    ```
    ffmpeg -i LostInTranslation.mkv -codec copy LostInTranslation.mp4
    ```
    From https://askubuntu.com/questions/396883/how-to-simply-convert-video-files-i-e-mkv-to-mp4
