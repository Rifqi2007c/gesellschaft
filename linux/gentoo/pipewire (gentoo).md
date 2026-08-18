### installing pipewire in gentoo without session manager (openrc)
- install: pipewire and wireplumber
	- `emerge --ask media-video/pipewire media-video/wireplumber`
	- try run with `gentoo-pipewire-launcher`
- run pipewire at start of seesion
	- put `gentoo-pipewire-launcher &` inside *.xinitrc* or similar

---
#gentoo 