for some reason obsidian zoom view reset to default after restart in wayland

### how to fix
- edit `obsidian.desktop` loacted in `/usr/share/applications`
	- `sudo nano /usr/share/applications/obsidian.desktop`
- change `Exec=/usr/bin/obsidian %U` to:
	- `Exec=/usr/bin/obsidian --enable-features=UsesOzonePlatform --ozone-platform-wayland %U`

----
#archlinux 