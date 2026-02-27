### setup git local and github repo
- ### make an access token
	- in github:
		- settings(profile) > devloper option
		- choose token classic
		- switch to no experation date
		- in select scope: tick **repo**
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


### obsidian
- download git extention