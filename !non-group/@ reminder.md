_"when switching from desktop to laptop or vice-versa"_

- drive
	- turn off current drive and turn on the other drive in `/etc/fstab`
- nvidia driver
	- when switching to device __with__ nvidia gpu:
		- add mkinitpcio MODULE. refer([[nvidia (archlinux)]])
		- add kernel parameter. refer([[nvidia (archlinux)]])
		- enable nvidia systemd services. refer([[nvidia (archlinux)]])
	- when switching to device __without__ nvidia gpu
		- remove all module that related to nvidia
		- remove all kernel parameter that relate to nvidia
		- disable all systemd services from nvidia

> if the user forgot to do so, this process can be done with arch installation media usb

---

_nothing can be done by feeling so sorry for myself_

_savor every moment_

_that\`s that and this is this_ 

_then is then, now is now_

---
#reminder