ffmpeg ussage
- convert
	- `-i <input> <output>`
	- `-c` to copy original properties like codec (optional)
		- example: `ffmpeg -i video1.mov -c video1.mp4`
- re-encoding: `-c:v <encoder>`
	- \<encoder>
		- `libx264` - High-quality H.264 (AVC)
		- `libx265` - High Efficiency Video Coding (HEVC/H.265)
		- `h264_nvenc` - Hardware-accelerated H.264 encoding using NVIDIA GPUs
		- `mpeg4` - Native mp4 encoder
			- example: `ffmpeg -i input.mp4 -c:v mpeg4 output.mp4`
- change fps
	- `fps=fps=\<int>`
		- example: `ffmpeg -i input.mp4 -filter:v fps=fps=30 output.mp4`
> `filter:v` = apply to video / video filter
- change resolution
	- `-vf scale=WIDTH:HEIGHT`
		- example: `ffmpeg -i input.mp4 -vf scale=1280:720 output.mp4`
- change audio bit depth
	- `-c:a <bit-depth>
	- option
		- 16 bit: `pcm_s16le`
		- 24 bit: `pcm_s24le`
	- example: `ffmpeg -i input.mp4 -c:a pcm_s24le output.mp4`
### convert with ProRes encoder (for davinci-reolve free version in linux)
```
ffmpeg -i input.mp4 -c:v prores_ks -profile:v 3 -c:a pcm_s24le output.mov
```
- ProRes profile `-profile:v <version>`

| version | flavor              | use case                                    |
| ------- | ------------------- | ------------------------------------------- |
| 0       | ProRes 422 Proxy    | Offline editing with small file sizes       |
| 1       | ProRes 422 LT       | Storage-constrained workflows               |
| 2       | ProRes 422 Standard | General high-quality video editing          |
| 3       | ProRes 422 HQ       | Post-production and mastering (Recommended) |
| 4       | ProRes 4444         | VFX and graphics requiring an alpha channel |
| 5       | ProRes 4444 XQ      | Extreme high-end dynamic range mastering    |

### convert for most device (tip)
in case of playback issue in some device
```
ffmpeg -i input.mkv -c:v libx264 -profile:v baseline -level 3.0 -pix_fmt yuv420p -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" -c:a aac -b:a 128k -movflags +faststart output.mp4
```
this will convert the video to be playable in **most device**
why?
- `-c:v libx264`: uses libx264 (H.264) codec
- `-profile baseline -level 3.0`: uses baseline profile of level 3 to restrict advance feature in H.264 codec for older device compability
- `-pix_fmt yuv420p`: set pixel format to 8-bit. high-end video often uses 10-bit color, which makes videos show a black screen or fail completely on older phones and QuickTime players
- `-vf "scale=trunc(iw/2)*2:trunc(ih/2)*2"`: ensures the video's width and height dimensions are perfectly divisible by 2. a hard mathematical requirement for the `yuv420p` pixel format
- `-c:a aac -b:a 128k`: uses aac for standard audio codec with a standard 128k quality
- `-moveflags +faststart`: moves the file's index metadata (moov atom) to the beginning of the file

---
#toys 