# vultr-w2k16-drivers-exported
Exported Drivers of Windows 2016 Backup from Vultr VM

```
Export-WindowsDriver -Destination "C:\Drivers\$((Get-WmiObject -Class win32_computersystem).Model)" -Online
```
