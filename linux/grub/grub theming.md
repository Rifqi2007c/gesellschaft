grub preview tool:
- grub2 theme preview
> when downloading `grub2-theme-preview` on arch, use the `qemu-desktop` package, `qemu-base` is not working on arch

### configure themes
examlpe theme
- in `/boot/themes/`
- make new folder with desired theme name
- content that need to be inside `<user-theme-folder>`
	- `theme.txt` - main config that to render grub theme
		- optional:
			- custom font in .pf2 format
			- picture for background, etc...

### turn font.ttf into font.pf2 format
- use `grub-mkfont`
- usage
	- `grub-mkfont -s <size int> -o <output-font.pf2> <input-font.ttf>`
- example: `grub-mkfont -s 16 -o font.pf2 font.ttf -v`
	- `-s` - size
	- `-o` - output
	- `-v` - print font propertise like name, size and type
> `-v` is use to see the font actuall name and what to put in `theme.txt`

### preview theme
- use grub2 theme preview
- usage
	- `grub2-theme-preview </path/to/theme.txt>`
- example: `grub2-theme-preview --grub-cfg /boot/grub/grub.cfg /boot/grub/themes/the-index/theme.txt --no-kvm --resolution 1920x1080`
	- `--grub-cfg` - use for putting what to display in theme preview entry menu
	- `--no-kvm` - launch qemu without hardware acceleration
	- `--resolution` - display preview in desired resolution

> regenerate grub config after done configuring/making theme

---
#linux 