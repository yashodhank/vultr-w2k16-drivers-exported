# vultr-w2k16-drivers-exported
## Exporting Drivers to `C:\Drivers`
Exported Drivers of Windows 2016 Backup from Vultr VM

```
Export-WindowsDriver -Destination "C:\Drivers\$((Get-WmiObject -Class win32_computersystem).Model)" -Online
```


## Importing Drivers from `C:\Drivers`

```
$infs = Get-ChildItem -Path "C:\Drivers\$((Get-WmiObject -Class win32_computersystem).Model)" -Filter "*.inf" -Recurse -File
foreach($inf in $infs){
    $inf.FullName
    pnputil.exe -i -a ""$inf.FullName""
}
```

### Archive provides only necessary VirtIO Drivers for your custom Windows Server 2016 Installation disk/iso to be imported using NTLite for Vultr
``
Filename:
Standard PC (i440FX + PIIX, 1996) 5-17-2020 2-30-11 PM.zip
```
