### take a bunch of file and do something
- `for f in *<file-format>; <any-command> with "$f" as the file name; done`
	- `for f in *<file-format>;`
	- after `;` put command with `"$f"` as file name
	- then after `;` at the end of command put `done`
- example with ffmpeg convert mkv to mp4
```
for f in *.mkv; do ffmpeg -i "$f" -c copy "${f%.*}.mp4"; done
```
> `${f%.*}.mp4` takes original name and replace * with other format