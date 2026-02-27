### 1.install font
## 2.install flow launcher
## 3.install scoop and git
```
> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
> Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
> scoop install git
```
## 4. install komorebi
```
> scoop bucket add extras
> scoop install komorebi whkd
```
## 5.install yasb reborn
## 6.install pywal
```
> winget install Python.Python.3.13
> scoop install imagemagick
> pip install pywal colorthief colorz haishoku
```
* Install winwal.psm1
* add it to $PROFILE
```
> code $PROFILE
> Import-Module .\<path to\winwal.psm1
```
