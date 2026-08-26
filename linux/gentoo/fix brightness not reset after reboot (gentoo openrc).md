make a script to change brightness that run after boot and before poweroff

### make the script
- make sure `local` service is added in OpenRC
	- `rc-update add local default`
- look at backlight directory name in `/sys/class/blacklight`
	- `ls /sys/class/backlight`
- make a script to run at start inside in `/etc/local.d`
example script:
```
#!/bin/sh
backlight_sys_dir="/sys/class/backlight/amdgpu_bl0" # Replace with your backlight device
if [ -f /var/lib/backlight/brightness ]; then
    cat /var/lib/backlight/brightness > ${backlight_sys_dir}/brightness
fi
```
- make a script to run before poweroff in `/etc/local.d`
example script:
```
#!/bin/sh
backlight_sys_dir="/sys/class/backlight/amdgpu_bl0" # Replace with your backlight device (e.g., amdgpu_bl0)
if [ ! -d /var/lib/backlight ]; then
    mkdir -p /var/lib/backlight
fi
cat ${backlight_sys_dir}/brightness > /var/lib/backlight/brightness
```
---
#gentoo 