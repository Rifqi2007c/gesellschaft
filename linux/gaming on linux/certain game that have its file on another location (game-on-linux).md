> this note is for steam game installed in a windows drive
> this note comes after [[play steam games from windows drive (game-on-linux)]] note

some games have its user data installed/writen on a folder where steam proton/wine cant access or user wanted to use the game save from windows to avoid redownloading or moving the gamefile

> most game require updating or file validating after doing any of these steps
### use mount --bind (recommend)
- mount windows drive first
- make the game file folder in where linux or proton/wine for that game would read with same folder name as what the game will make in windows
- to test it out:
```
mount --bind /mnt/windows/path/to/origin /path/to/mount-bind
```
- example with osu!lazer:
	- windows osu!lazer stored file in windows: `C:\\Users\<user>\AppData\Roaming`
	- where osu!lazer read in linux: `/home/.local/share`
		- make osu folder in `~/.local/share/`
		- mount --bind from folder to folder
```
mount --bind /mnt/windows/Users/rifqi/AppData/Roaming/osu /home/rifqi/.local/share/osu
```

### make symlink using windows symlink (recommend if using steam proton/wine)
if playing game through linux steam proton, it will create compatdata for that game the file ususally in the same location/drive with where the game is installed
> make sure cmd or powershell is open with administrator
- cmd: `mklink /d "C:\Path\To\Symlink" "C:\Path\To\OriginalFolder"
	- `mklink` with `/d` flag
- powershell: `New-Item -ItemType SymbolicLink -Path "C:\Path\To\Symlink" -Target "C:\Path\To\OriginalFile"`
- gui (third-party app): [link shell extension](https://schinagl.priv.at/nt/hardlinkshellext/linkshellextension.html)
	- in explorer on the game file:
		- right click and choose: Pick Link Source
	- in explorer to where the symlink needed to be
		- right click and choose: Drop As... > Junction

### make linux symlink
- create a symlink from where the game file is and put it in `/media/gamedisk/Program\ Files\ \(x86\)/Steam/steamapps/compatdata/<STEAM-GAME-ID>/pfx/drive_c/users/steamuser/AppData/`
- you can find steam games ID in the game store page
	- `sudo ln -s /path/to/your/TARGET_LOCATION/ /path/to/your/LINK_FOLDER/`
	- `TARGET_LOCATION`: where the file is located
	- `LINK_FOLDER`: where the file needed to be
> sudo is needed because the is outside user home folder or `~`
### example games
- ##### limbus company
```
> sudo ln -s /mnt/windows/Users/rifqi/AppData/LocalLow/Unity/ /mnt/windows/Program\ Files\ \(x86\)/Steam/steamapps/compatdata/1973530/pfx/drive_c/users/steamuser/AppData/LocalLow/
```
limbus company user data is in installed in `LocalLow/Unity` so create a symlink from there to `1973530/pfx/drive_c/users/steamuser/AppData/LocalLow`
- 1973530 is limbus company steam game id

----
#linux #game-on-linux 