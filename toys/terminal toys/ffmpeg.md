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
---
#toys 