### installing pipewire in gentoo without session manager (openrc)
- install: pipewire
	- build system with `pipewire` and `sound-server` use flag or `emerge --ask media-video/pipewire`
	- try run with `gentoo-pipewire-launcher`
- run pipewire at start of seesion
	- x11
		- put `gentoo-pipewire-launcher &` inside *.xinitrc* or similar
	- wayland
		- launch `gentoo-pipewire-launcher` with whatever wayland wm/de is used

---
#gentoo 