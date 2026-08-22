commit, push and sometime pull

### to update git repository
- add new file if there's any: `git add .`
- commit after every changes made: `git commit -a -m "messages"`
- update remote repository: `git push -u origin <branch>`

### to pull or clone repo to the latest version if on different device
- on new device: `git clone <repo-url>`
- on device with repo already cloned: `git pull`
#### git pull may not work. use fetch instead
- `git fetch --all`
- backup (optional): `git branch <new-backup-branch-name>`
- `git reset origin/<branch>`
	- if this not work use `--hard`