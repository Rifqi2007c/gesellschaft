
### dependecies needed before install
- linux-headers
	- `sudo pacman -S linux-headers`
### driver and model
choose one:

| nvidia-open<p>nvidia-open-lts<p>nvidia-open-dkms | 16 series and newer |
| ------------------------------------------------ | ------------------- |
| nvidia-580xx-dkms(aur)                           | 10 series and lower |
- other package
	- egl-wayland
	- lib32-nvdia-utils
	- lib32-opencl-nvdia
	- nvidia-settings
	- opencel-nvidia
	- nvidia-utils
- [guide](https://wiki.archlinux.org/title/NVIDIA)
or use this for easier setup -> https://github.com/Frogging-Family/nvidia-all
- after install
	- add `nvidia nvidia_modeset nvidia_uvm nvidia_drm` inside `MODULE` in `/etc/mkinitcpio.conf`
		- `MODULES=(nvidia nvidia_modeset nvidia_uvm nvidia_drm)`
	- refresh mkinitcpio. `mkinitcpio -P` 
> this also can can be done before install the driver
> if done before installing, refreshing mkinitcpio is not needed since the installing process already done it
### [hyprland + nvidia gpu](https://wiki.hypr.land/Nvidia/)
- add thesee enviroment table in hyprland.conf
```
env = LIBVA_DRIVER_NAME,nvidia
env = XDG_SESSION_TYPE,wayland
env = GBM_BACKEND,nvidia-drm
env = __GLX_VENDOR_LIBRARY_NAME,nvidia
```

### kernel parameter
- in `/etc/default/grub` add these parameter inside `GRUB_CMDLINE_LINUX_DEFAULT=" <parameter> "`
	- nvidia_drm.modeset=1 (important)
	- nvidia_drm.fbdev=1 (optional)
	- nvidia.NVreg_PreserveVideoMemoryAllocations=1 (optional)

### systemd service (disable this when switching to different device with different gpu but with the same drive)

- nvidia-resume
- nvidia-hibernate
- nvidia-suspend

---
#archlinux 