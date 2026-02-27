### install
```
wsl --install archlinux
```
### setup prerequisite package
- sudo
- visudo
- nano or any other text editor
```
pacman -S sudo visudo nano
```
> update system is recommended before start:
> `pacman -Syu`
### create root password
```
passwd
```
### create user
```
useradd -m -s <SHELL-LOGIN> <USERNAME> 
```
- *pointer*
  - `-m`/`--create-home` create home
  - `-s`/`--shell` assign default shell. path/to/shell (use `which` to find shell directory)
  - `-G`/`--groups` create group
- create user password
```
passwd <USERNAME>
```
### add user to sudoers
- add user to `wheel` group
```
usermod -aG wheel <USERNAME>
```
- edit /etc/sudoers
```
EDITOR=nano visudo
```
or
```
sudo nano /etc/sudoers
```
  - add `<USERNAME> ALL=(ALL:ALL) ALL` under `## User privilage specification`
  - uncomment `%whell ALL=(ALL:ALL) ALL`

### make new user deafault user
- edit `/etc/wsl.conf`
```
nano /etc/wsl.conf
```
- add:
```
[user]
default=<USERNAME>
```
----
#windows  