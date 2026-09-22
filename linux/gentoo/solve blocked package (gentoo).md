some package may cause other package to cant be install and cant update @world if there are dependecies error

### how to solve
scenario: trying to update system with `emerge --ask --changed-use --deep @world` then there a blocked package error.
- look for output at the top where it say `[blocks B  ]<package cause> (<reason and which package is blocked>)`
	- example
```
[blocks B      ] sys-apps/dbus[abi_x86_32,-X] ("sys-apps/dbus[abi_x86_32,-X]" is soft blocking games-util/steam-launcher-1.0.0.87)
```
in this example: `sys-apps/dbus` is blocking `games-utils/steam-launcher` because it need `abi_x86_32` and `X` use flag to coexist with `games-utils/steam-launcher`
#### fix step
- make new file for `sys-apps/dbus` in `/etc/portage/package.use`
- inside the file write `sys-apps/dbus abi_x86_32 X`
- try emerge @world

---
#gentoo 