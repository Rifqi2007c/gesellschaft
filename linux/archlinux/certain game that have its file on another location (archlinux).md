> this note is for steam game installed in a windows drive
> this note comes after [[play steam games from windows drive (archlinux)]] note

some games have its user data installed/writen on a folder where steam proton/wine cant access so it means user have to move the game file or redownload
### how to tackle this problem
- create a symlink from where the game file is and put it in `/media/gamedisk/Program\ Files\ \(x86\)/Steam/steamapps/compatdata/<STEAM-GAME-ID>/pfx/drive_c/users/steamuser/AppData/`
- you can find steam games ID in the game store page
	- `sudo ln -s /path/to/your/TARGET_LOCATION/ /path/to/your/LINK_FOLDER/`
	- `TARGET_LOCATION`: where the file is located
	- `LINK_FOLDER`: where the file needed to be
> sudo is needed because the is outside user home folder or `~`
### example games
- ##### limbus company
```
> sudo ln -s /media/gamedisk/Users/rifqi/AppData/LocalLow/Unity/ /media/gamedisk/Program\ Files\ \(x86\)/Steam/steamapps/compatdata/1973530/pfx/drive_c/users/steamuser/AppData/LocalLow/
```
limbus company user data is in installed in `LocalLow/Unity` so create a symlink from there to `1973530/pfx/drive_c/users/steamuser/AppData/LocalLow`
- 1973530 is stea game id

----
#archlinux 