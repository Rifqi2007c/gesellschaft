### execute .ps1 script (faster method using *task scheduler*)
- create task in *task scheduler library* folder
- add triger set begin task to *at log on*
- add action set to *start a program* and put *pwsh.exe* or *powershell.exe* in *program/script*
> if powershell 7 use pwsh.exe
> if powershell 5 use powershell.exe
- add this *agruments*
```
-NoProfile -ExecutionPolicy Bypass -File "<PATH\TO\SCRIPT.ps1>"
```
----
#windows 