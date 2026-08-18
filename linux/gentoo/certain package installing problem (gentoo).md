the user may face with **masked** or **licensing** issue when installing

### solve masked package
- add new file to `/etc/portage/package.accept_keywords` with a file name depend on the package that were trying to be installed
	- exmaple: if the package name is `nwg-look` the the file name should be the same without the back: (without `app-misc/` in this case)
- edit the new file:
	- inside the file
```
app-misc/nwg-look ~amd64
```
> `~amd64` might be different depent on cpu architecture

### solve licensing issue
- edit `/etc/portage/package.accept_license`
- add: `<repo/package-name> <licence>` 
	- licence name base on what error output display
	- license example: 
		- Obsidian-Eula
		- Sporify

---
#gentoo 