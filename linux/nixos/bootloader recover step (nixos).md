when a drive that contain nixos is taken out and put in a new a place or put back in, the computer bios may not be able to boot it right away.

### fix the bootloader from live usb environment (nixos)
1. mount root(`/`) to `/mnt`
2. mount boot(`/boot`) to `/mnt/boot`
3. run: `sudo nixos-generate-config --root /mnt` to update `hardware-configuration.nix` with the new drive location
4. reinstall nixos: `sudo nixos-install`
5. remove the usb and reboot
> `nixos-install` will not delete present content in said drive