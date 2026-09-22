hex dump viewer, editor and converter
### view file in hex
```
xxd <input-file>
```

### edit file in hex
- #### any editor (recommend)
- read file hex dump then print its output into .txt file
```
xxd <input-file> | output.txt
```
- then edit output.txt with any file editor
> output.txt can be any name
#### with vim/neovim
- open a file with vim/nvim: `vim <input-file>`
- in vim with that file open:
	- type: `:%!xxd` to start editing
	- type: `:%!xxd -r` to convert back to binary
	- then save
### convert file into binary
- take hex dump code that are written in inside .txt then convert to its binary form
```
xxd -r <input-file> <output-file>
```


checkout:
- [[fixing corrupted file from hex dump]]

---
#cybersecurity 