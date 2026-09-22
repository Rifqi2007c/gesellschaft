### pipewire system
the system need pipewire, sound-server, dbus
- add package.use for `media-video/pipewire` with `sound-server` and `dbus` flag
	- or use use pipewire in make.conf
```
USE=" pipewire sound-server dbus"
```
- then, add package.use for `media-libs/libpulse` with `glib` flag
- add package.use for `www-client/firefox` with `pulseaudio`, `system-pipewire`, `dbus`, `clang` flag
- recompile entire system package or individually
	- individually: `emerge --ask <package-name>`
	- entire system package: `emerge --ask --changed-use --deep @world`
> the user might want to update entire system package if the user is using USE flag inside `make.conf`

---
#gentoo 