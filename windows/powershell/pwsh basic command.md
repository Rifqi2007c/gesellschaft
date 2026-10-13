### winget (windows packages manager)
- search packages
```
winget search "<PACKAGE NAME>"
```
- install packages
```
winget install <PACKAGE ID> --source winget
```
- uninstall
	same as install package but replace install with uninstall
---
### basic command
#### change directory
- `cd <location>`
	- example: `cd C\:Users\user\Download`
#### create file
- `New-Item "<any-filetype> -ItemType file"`
	- example: `New-Item "hello.txt" -ItemType file`
- option
	- `-Path` make the file in specific location
	- `-Force` force
#### remove file
- `Remove-Item "<any-file">`
	- example: `Remove-Item hello.txt`
- option
	- `-Recurse` remove file recursely (use for remove directory)
	- `-Force` force
----
#windows #powershell 