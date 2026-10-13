### fixing with diskpart and bcdboot
- from windows live usb, press SHIFT + F10 to open CMD
- in CMD
	- run `diskpart`
		- in `diskpart`
		- `list disk`
		- select the disk where windows is installed
			- example: `list disk 0`
		- `list vol`
			- select the FAT32 volume
				- example: `select vol 1`
			- then assign a letter so it can be use with bcdboot
				- `assign letter=Z` (the use can use any letter that are not used in other volume)
		- `exit`. exit diskpart
	- run `bcdboot C:\Windows /s Z: /f ALL` to create the new bootloader file
		- C: and Z: is depend on what diskpart output when `list vol`
		- C: is where windows is installed
		- Z: is where the bootloader is
#### if there is no FAT32 volume
create it. using diskpart
- in diskpart
	- select the disk
	- list partition. `list partition`
	- select partition. example: `select partition 2`
	- make new partition by shrinking it by 100MB to make space for bootloader
		- `shrink desire=100`
	- make that partition into an efi partition and format it into FAT32 file system
		- `create partition efi`
		- `format quick fs=fat32 label="System"`
	- assign the letter
	- exit diskpart
- run bcdboot. `bcdboot C:\Windows /s Z: /f ALL`

if not working might need to checkout: [[fix windows bootloader disk conflict]]

---
#windows #cmd 