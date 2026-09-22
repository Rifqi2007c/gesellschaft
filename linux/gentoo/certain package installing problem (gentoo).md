the user may face with **required use flag**, **masked** or **licensing** issue when installing

### solve required use flag issue
- look for what the package need in the emerge ouput
	- in may look like this: `media-libs/libglvnd-<version> X`
	- this mean `media-libs/libglvnd` need to be compile with X flag
- make new file in `/etc/portage/package.use` with any name or base on package(recommend)
- inside the file write the package name and its required flag at the end
	- example with libglvnd that required X flag: `media-libs/libglvnd X`
> you can ignore or add the version.
> if the package required python flag, write python_targets_python3_xx (replace x with python version) add the end

#### autowrite option (usefull for when there are alot of required use flag)
- use `dispatch-conf`
- press u option to update with the requirement portage config
> there is also `etc-update` but that one is not recommended and might break emerge

### solve masked package
usually heppend becuase the package that were trying to emerge is from non-official repository
- #### accept the entire repo
	- make new file in `/etc/portage/package.accept_keywords` with any name or base on repository(recommend)
	- inside the file write `*/*::<repository name>`.
		- example for guru repository: `*/*::guru`
- #### accept one by one
	- make new file in `/etc/portage/package.accept_keywords` with any name or base on package(recommend)
	- inside the file write the full package name
		- example for pywal16: `x11-misc/pywal16`
> it is possible to make portage use accept unstable version of package by putting `~amd64` at the end. example: `x11-misc/pywal16`

### solve licensing issue
- edit `/etc/portage/package.accept_license`
- add: `<repo/package-name> <licence>` 
	- licence name base on what error output display
	- license example: 
		- Obsidian-EULA
		- Sporify

### solve emerge package verification failed
- delete `/var/cache/distfiles/<failing-file-name>`
- example: `rm /var/cache/distfiles/doasedit-1.0.9.tar.gz._checksum_failure_.ki4sjt6y`

---
#gentoo 