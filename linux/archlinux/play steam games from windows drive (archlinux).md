### configuring and mounting the NTFS partition
- ##### install package dependecies
	- `ntfs-3g`
- ##### create a mount point
	- `sudo mkdir /media/gamedisk`
		gamedisk is just a folder name which means it can be name it whatever
- ##### find linux user, group ID and drive UUID where windows is installed:
	- find ID:
		- `id -u` find user id
		- `id -g` find group id
	- find drive UUID
		- `lsblk -f`
		fine line where theres `TYPE="ntfs"`
- ##### editing fstab to add windows drive
	- fstab located at `/etc/fstab`
		- add `UUID=<UUID> /media/gamedisk ntfs uid=<USER-ID>,gid=<GRUOP-ID>,rw,user,exec,umask=000 0 0`
		- example
```
> UUID=38CE9483CE943AD8 /media/gamedisk ntfs uid=1000,gid=1000,rw,user,exec,umask=000 0 0
```
- ##### reboot
	- `sudo reboot`
### preventing NTFS read error
Due to the nature of NTFS, creating files/folders with names that are invalid on Windows will cause disk errors (leading to games that don't launch). The most common issue is a : (colon) character in filenames that Proton creates on the NTFS disk.
- create a symlink
```
> mkdir -p ~/.steam/steam/steamapps/compatdata
> ln -s ~/.steam/steam/steamapps/compatdata /media/gamedisk/Steam/steamapps/
```
> if steamapps folder doesnt exit (in my case it didnt), create it

----
#archlinux 

source:
https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows