### steam
- install steam: `sudo pacman -S steam`
- steam will ask which `lib-<driver>` is needed to install. install according to user GPU

### play steam windows(.exe) games
not all game support linux natively. to play windows(.exe) games, a compabilty layer is needed.

- turn on comptibility: steam settings > compabitility, enable it
	steam will install proton and restart

### command and tools that may help with the performance
- gamemode
- lib32-gamemode
- gamescope
```
sudo pacman -S gameode lib32-gamemode gamescope
```
- ##### play game with gamemode and gamescope
- go to properties on the game that may needed this tools
- in general, there\`s a launch option input bar
	- put both or individual tools in the bar
		- individual: `gamemoderun %command%` or `gamescope -W 1920 -H 1080 -- %command%`
		- both: `gameoderun gamescope -W 1920 -H 1080 -- %command%`

### gamemode
- gamemoded test
	- `gamemoded -t` to test the gamemode config file and see if there any error
- configuring
	- `gamemode.ini` located in `/etc/`
	- if the file not there create it: `sudo touch /etc/gamemode.ini`
		- the example config is available at https://github.com/FeralInteractive/gamemode/blob/master/example/gamemode.ini
		- copy and paste it
	- recomended configuration
		- `renice=11`
			- 11 is the max amout but you can go beyond it by adding `<username> - nice -20` at the end of `/etc/security/limits.conf`
		- `park_cores=no`
		- `pin_cores=yes`
> check https://wiki.archlinux.org/title/GameMode for more information
### gamescope
- set render resolution
	- `-W <int>`
	- `-H <int>`
		- example: `gamescope -W 1920 -H 1080`
- wayland backend support
	- `--backend wayland` or `--expose-wayland`
- limit fps
	- `-r <int>`
		- example: `gamescope -r 60`
### known steam bug
- steam proton severe stutering after 20-30 minute on VULKAN/DXVK games
	- add `LD_PRELOAD="` in the launch options
### launch option summary
```
LD_PRELOAD="" gamemoderun gamescope  --backend wayland -W 1920 -H 1080 -r 60 --  env LD_PRELOAD="$LD_PRELOAD" %command%
```

----
#archlinux 