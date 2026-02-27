### obsidian support
- https://github.com/poach3r/pywal-obsidianmd

### alacritty support
- https://github.com/egeesin/pywal2alacritty

### gtk3/4
- create pywal css template in `.config/wal/template/`
	- name can be whatever the user want. example: `custom-gtk3.css`
- generate pywal color
- make new Theme folder with any name inside `.themes` folder. example: `PywalTheme`
- inside `PywalTheme folder` create a folder named `gtk-3.0`
- create symlink with `-sf` in the command from `~/.cache/wal/custom-gtk3` to `~/.themes/PywalTheme/gtk-3.0` with the file named `gtk.css`
	`ln -sf ~/.cache/wal/custom-gtk3.css ~/.themes/PywalTheme/gtk-3.0/gtk.css`
- reload pywal

### neovim(lazyvim)
- ##### using neopywal plugin
- make two .lua file, example: `color.lua` and `neopywal.lua`
- in color.lua add the plugin:
```
return {
  "RedsXDD/neopywal.nvim",
  name = "neopywal",
  lazy = false,
  priority = 1000,
  opts = {},
}
```
- restart nvim to install the plugin
- in neopywal.lua add neopywal colorscheme loader
```
return {
  -- Configure LazyVim to load neopywal as the default colorscheme
  {
    "LazyVim/LazyVim",
    opts = {
      colorscheme = "neopywal",
    },
  },
}
```
- restart nvim

----
#archlinux 