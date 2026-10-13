some windows install might have a problem that output "mshtml.dll may not comapatible or corrupted" went trying to launch a game

### how to fix (option 1)
- open cmd with administrators
- run `sfc /scannow` to check and fix
- if that doesn't fix it try: `DISM /Online /Cleanup-Image /RestoreHealth` to download the fix from microsoft first then `sfc /scannow` to check

### how to fix (option 2)
- download windows iso file
- right click and select mount
- open cmd with administrators
- run `dism /Get-WimInfo /WimFile:E:\sources\install.wim`
	replace E with the right drive letter
- look through the list to find exact windows index number
- run `dism /Online /Cleanup-Image /RestoreHealth /Source:WIM:E:\sources\install.wim:1 /LimitAccess` to start the repair
	replace E with the right drive letter. replace 1 with the right index number
- run: `sfc /scannow` to check corrupted file

### how to fix (option 3)
**this step require second windows device**
- in second windows device copy the **mshtml.dll** file to a usb drive (or smililar way)
	- file location: `C:\Windows\System32\mshtml.dll`
- in the windows device that have broken mshtml.dll file delete that file by:
	- take ownership of the file to make windows let the user delete the file
		`dism /Online /Cleanup-Image /RestoreHealth /Source:WIM:E:\sources\install.wim:1 /LimitAccess`
	- grant full control permission of that file
		`icacls C:\Windows\System32\mshtml.dll /grant administrators:F` 
	- rename the old .dll to as something else to backup
			`ren C:\Windows\System32\mshtml.dll mshtml.dll.bak`
	- swap the file / put the .dll file from second windows device
	- reboot

#windows