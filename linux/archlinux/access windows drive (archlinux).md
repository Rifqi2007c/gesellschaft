### manual
##### package requirement
- ntfs-3g 
`sudo pacman -S ntfs-3g`

- mount windows drive to `/mnt`
	`sudo mount /dev/<sdX> /mnt`
	- replace `<sdX>` to your windows drive name
	- use `lsblk` to check
- cd to `/mnt`
> you need to make yourself an owner of the file that you take from windows drive:
> `sudo chown -R <username> <to/file/destination>`
### fstab (auto mounting)
- similar to [[play steam games from windows drive (archlinux)]]
----
#archlinux 