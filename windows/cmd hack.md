### make windows 11 show more option on the context menu(right click)
- open cmd and put this command:
	```
	reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
	```
- restart file explorer
### remove/add bin icon without activation
- open cmd and put this command:
  - remove
```
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\HideDesktopIcons\NewStartPanel" /v "{645FF040-5081-101B-9F08-00AA002F954E}" /t REG_DWORD /d 1 /f
  ```
   - add
```
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\HideDesktopIcons\NewStartPanel" /v "{645FF040-5081-101B-9F08-00AA002F954E}" /t REG_DWORD /d 0 /f
```
- refresh from context menu
### windows activation hack
- open cmd type:
  
```
irm https://get.activated.win | iex
```
- there will be bunch of option, choose.
> guide/shoutout video by [yegna media](https://www.youtube.com/@yegnamedia1) - [activate windows 10/11 tutorial](https://www.youtube.com/watch?v=Um_cS1hzRB8&list=WL&index=2)
----
#windows 