record base note(rifqi). game wont launch on linux while Im on gentoo with btrfs filesystem
while having the game on windows drive

solution
- move steam game to linux partition the move it back to windows
- delete steam compatdata of that game

goal
have the game on windows partition/drive while using linux(gentoo)

probable cause
- something have to with btrfs
- (most likely) fixing the corrupted drive with ntfsfix and chkdsk

note
- (most likely) fixing the corrupted drive with ntfsfix and chkdsk
I was trying to mount windows drive using ntfs3 but failed and with demsg telling the drive have corrupted drive. fixing it with ntfsfix give it a new error and chkdsk also didnt fix it.

before that, the windows drive completely corrputed to the it point windows cant boot. that happend because of I was being lazy and want to take some storage from windows partition, instead of using windows tool I just use cfdisk that come preinstalled in gentoo live installation media.

then I try using ntfsfix to fix it then windows is bootable again

----
#linux #rbn #game-on-linux 