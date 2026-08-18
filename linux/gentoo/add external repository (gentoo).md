certain package like obsidian and spotify is not available in gentoo base repo, the user need to add the external one

### adding repository
- install `eselect repository`
	- `emerge --ask app-eselect/eselect-repository`
- `eselect repository list`
	- to list all the available repo and its name
- enable repository
	- `eselect repository add <repo-name>`

--- 
#gentoo 