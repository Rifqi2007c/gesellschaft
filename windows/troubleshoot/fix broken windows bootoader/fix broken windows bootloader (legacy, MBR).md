### fixing with bootrec
- from live windows usb, press SHIFT + F10 to open CMD
- run these command:
```
bootrec /fixmbr
bootrec /fixboot
bootrec /scanos
bootrec /rebuildbcd
```
> if `bootrec /fixboot output` "Access is denied" run: `bootsect /nt60 sys` the try `bootrec /fixboot` again

#### if bootrec /scanos and /rebuildbcd find 0 windows installation
run these command:
```
bcdedit /export C:\BCD_Backup
c:
cd boot
attrib bcd -s -h -r
ren c:\boot\bcd\bcd.old
bootrec /rebuildbcd
```

if not working might need to checkout: [[fix windows bootloader disk conflict]]

---
#windows #cmd 