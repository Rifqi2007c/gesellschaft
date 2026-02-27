### from CMD (windows)
- open cmd with administrators
- type: `bcdedit /enum firmware`
	to list all the boot entries name and `<identifier>`
- type: `bcdedit /delete <identifier>`

### from linux terminal (efibootmgr)
- ##### required package
	- `efibootmgr`
- type: `sudo efibootmgr`
	to list all the boot entries name and `<identifier>`
- type: `sudo efibootmgr -b <identifier> -B`

----
#BIOS