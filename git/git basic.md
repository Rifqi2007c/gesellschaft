# git

- ### clone
	clone repository from github or other git services
- `git clone <repo url>`
- example: `git clone https://github.com/Rifqi2007c/hyprland.git`
> there is three type of git repo url.
- HTTPS (basic cloning)
- SSH (cloning with key if the user have it and if the repo need it)
- Github CLI (for git cli user)

- ### add
	add file to git repo (must do if new file is added to the git repo)
- usage: `git add <file>`
	- you can do `git add .` to add all new file to git repo
- example: if there is a file call `python.py` on the git folder then,
	`git add python.py`

* ### commit
	commit to new changes to local git repo
* usage: `git commit <option>`
* option:
	- `-m <"messages">` messages. `commit "messages"`
	- `-a` auto stage all track file (without this option you have to do it manually)
* example: `git commit -a -m "messages"`

- ### push
	push an update to server git repo from local git repo
- usage: `git push <option> origin <branch>`
- option:
	- `-u / --set-upstream` link local git repo to server git repo **(must do)**
	- `-f / --force` overwirte server repo history with local one **(caution: will delete your previous work on the remote repository)**
		- use case: if git cant push then user may force it but make sure the there is no important work on the server repo or make sure local repo is updated before adding changes
- example: `git push -u origin main`
- example2: `git push -u -f origin main`

- ### branch
	make backup branch
- usage: `git branch <new-backup-branch-name>`

* ### pull
	update local git repo from server git repo
* usage `git pull`

- ### fetch
	update remote tracking branches
- usage: `git fetch`
- option:
	- `--all` fetch the absolute latest history and file from remote repository

- ### reset
	reset local branch pointer to match the remote version perfectly.
- usage: `git reset origin/<branch>`.
- option:
	- `--hard` force reset. *will permanently delete all uncommitted local changes and unpush commits*

- ### remote
	manage connection between local repo and server repo
- usage:
	- `git remote add <name> <url>` connect local repo to server repo
	- `git remote -v` list existing remote
	- `git remote show <branch>` provides detailed information about a specific remote
	- `git remote set-url <branch> <new-url>` updates the URL for an existing remote
		- this option can be used for if git repo were previously clone using HTTP and the user want to use SSH-key.