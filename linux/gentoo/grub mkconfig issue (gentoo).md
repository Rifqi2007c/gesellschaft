tag:#gameonlinuxif `grub-mkconfig -o /boot/grub/grub.cfg` not applying new configuration it means /boot might be root hidden directory instead of the real /boot or boot partition

### workaround
- `umount /boot`: unmount /boot
- refresh grub config: `grub-mkconfig -o /boot/grub/grub.cfg`

--- 
#gentoo