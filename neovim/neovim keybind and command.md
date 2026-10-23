#### insert mode
- i
- exit insert mode: esc
#### command panel
- :
#### save
- `:w` save
- `:wq` save and quit
> can be use with `!` to force. `:w!`
#### quit
- `:q` quit one file
- `:qall` quit all
> can be use with `!` to force quit. `q!`
#### copy/paste
- requirement: `wl-clipboard`(wayland) or `xorg-xclipboard`(X11)
- keybind
	- copy: y (yanked)
	- paste: p
#### select entire file for something
- gg then VG
#### delete selected
- d
#### delete entire line
- put cursor on a line then press dd
#### change tab
- \[ or \] then b
- if newtab is created using `:tabnew` then gt (next) or gT (previuos)
#### delete buffer (similar to tab)
- `:bd` or `:bdelete`
> recommend to use with bufferline plugin
#### change focus
- ctrl + w, then w or \<arrow key\>
#### find text
- /
	- n (go to next sequence)
	- N (go to previosus sequence)
#### jump to line
- `:<any-number>`
- type any number then gg
- type any number then G

#### add whitespace at the start of mutiple line
- select the line then, SHIFT + >
### manipulate selected text
-	#### replace text
	- :`:%s/old/new/g`
		- remove % to select individually. the earliest in the text file will be selected first
	- :`:<num>,<nums>/old/new/g`
		- select and replace base on line number choosen. example: `10,20s/old/new/g`
- ##### delete selected
	- :`:g/selected-text/d`
- #### add text at the start or end of the line
	- start: `:g/selected-text/s/^/new-text`
	- end: `:g/selected-text-text/s/$/new-text`
----
#neovim