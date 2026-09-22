### step
- extract downloaded image file: `disk-image.dd.gz`
```
gunzip disk-image.dd.gz
```
output: `output.dd` or whatever the file name its with .dd format
- list its strings then use grep to minimize the result to find flag easier with a keyword the resembalance the file like pico and CTF
	- `strings output.dd | grep pico`
> gunzip, strings and grep should already come with most linux distro

---
#cybersecurity 