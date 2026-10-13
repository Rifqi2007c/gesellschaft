### mbr to gpt
in instance where the user installed windows using mbr but then the bootloader is broken but after try to fix it, now windows tring to boot lecgacy system system with uefi(gpt)

this can happend if the user motherboard support for both

reference:
![[fix-boot-conflict-reference.jpg|400]]

### use built-in windows mbr to gpt tool (mbr2gpt)
- in live windows usb, press SHIFT + F10 to open CMD
- run:
	- `mbr2gpt /validate`
	- `mbr2gpt /convert`
> if mbr2gpt output "mbr2gpt failed to update ReAgent.xml", dont worry about it. it just config file that track WinRE location
- #### update the boot cinfiguration data
	- use diskpart to identify and assign a letter to new FAT32 volume created by mbr2gpt
	- rebuild the bootloader with bcdboot
```
bcdboot C:\Windows /s Z: /f UEFI
```
> make to replace C: and Z: to what diskpart ouput when `list vol`

---
#windows #cmd 