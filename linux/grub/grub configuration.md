grub config location:
- `/etc/default/grub` - grub basic config file
- `/etc/grub.d/` - contain boot sequence like: 00_header, 10_linux, ...
- `/boot/grub` - conatain grub esential:
	- `/themes`
	- `/theme`
	- `/grub.cfg`
> modifying `grub.cfg` is not recommended and it also a generated file by grub

### grub basic configuration (`etc/default/grub`)
- `GRUB_GFXMODE=` - grub resolution
- `GRUB_THEME=` - give grub custom theme file
- `GRUB_DISABLE_OS_PROBER=` - grub os prober to detect other OS (uncomment and set to false to turn it on)
> regenerate grub config after every changes made
> in arch: `sudo grub-mkconfig -o /boot/grub/grub.cfg`
## grub fun stuff
check [[grub theming]] for making custom theme
### grub display ascii art on when booting into OS
- in `/etc/grub.d/10_linux` config file
	- put ascii art using echo under Loading ramdisk

```
EOF
  if test -n "${initrd}" ; then
    # TRANSLATORS: ramdisk isn't identifier. Should be translated.    <--- echo ramdisk
    message="$(gettext_printf "Loading initial ramdisk ...")"
    initrd_path=
    for i in ${initrd}; do
      initrd_path="${initrd_path} ${rel_dirname}/${i}"
    done
    sed "s/^/$submenu_indentation/" << EOF
	echo	'$(echo -e "$message" | grub_quote)'
	initrd	$(echo $initrd_path)
EOF   <--- add EOF
echo echo   <--- use (echo echo) to make space between line
echo echo '" (0) (0) "' <--- put ascii art here and display
echo echo '"    W    "' << EOF    <--- at the end of the art put: << EOF
```
- regenerate grub config and check `grub.cfg`
	- should look like this under linux boot menu entry(`menuentry`):

```
### BEGIN /etc/grub.d/10_linux ###
menuentry 'Arch Linux' --class arch --class gnu-linux --class gnu --class os $menuentry_id_option 'gnulinux-simple-25d3b723-d1e0-4369-b492-9eb3628d1e49' {
	load_video
	set gfxpayload=keep
	insmod gzio
	insmod part_gpt
	insmod fat
	set root='hd0,gpt1'
	if [ x$feature_platform_search_hint = xy ]; then
	  search --no-floppy --fs-uuid --set=root --hint-bios=hd0,gpt1 --hint-efi=hd0,gpt1 --hint-baremetal=ahci0,gpt1  F145-4748
	else
	  search --no-floppy --fs-uuid --set=root F145-4748
	fi
	echo	'Loading Linux linux-zen ...'
	linux	/vmlinuz-linux-zen root=UUID=25d3b723-d1e0-4369-b492-9eb3628d1e49 rw zswap.enabled=0 rootfstype=ext4 loglevel=3
	echo	'Loading initial ramdisk ...'
	initrd	/amd-ucode.img /initramfs-linux-zen.img
echo
echo " (0) (0) "         <---- ascii art
echo "    W    "
```

---
#linux 