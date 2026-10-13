### list stored UEFI boot option
```
bcdedit /enum firmware
```
### delete boot entries
```
bcdedit /delete {identifier}
```
> identifier is from what `bcdedit /enum firmware` output

---
#windows #cmd