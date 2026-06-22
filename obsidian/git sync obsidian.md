### setup git local and github repo
- ### make an access token
	- in github:
		- settings(profile) > devloper option
		- choose token classic
		- switch to no experation date
		- in select scope: tick **repo**
> after generating token **safe it somewhere, github only show it once**
- make new directory for your vault
- make new github repo
- follow intstruction in github repo that it give after creating a new repo

### make ssh key (for passwordless commit)
- install `openssh`
- generate key: `ssh-keygen -t ed25519 -C "<your@email.com>"`
	ssh key will be put inside `$HOME/.ssh`
- look at the generated key: `cat ~/.ssh/id_ed25519.pub`
- copy the key and paste it in github ssh key
	- settings(profile) > SSH and GPG keys
- verify key: `ssh -T git@github.com`
- update url if needed: `git remote set-url <branch> <ssh-url>`
	- example: `git remote set-url origin git@github.com:Rifqi2007c/hyprland.git`

### obsidian
- download git extention

video guide:
https://www.youtube.com/watch?v=PScdHzUiBLA&t=728s

---
#obsidian 