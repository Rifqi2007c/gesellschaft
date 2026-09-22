embed or extract file inside from another file(cover file)
### embed
```
steghide embed -cf <cover.jpg> -ef <secret.tx>t -p mysecretkey
```
- `-cf` input cover file to use
- `-ef` input secret file to embed inside cover file
- `-p` set password (optional)

### extract
```
steghide extract -sf img.jpg -p pAzzword
```
- `-sf` input file to extract
- `-p` input password (if required)

---
#cybersecurity 