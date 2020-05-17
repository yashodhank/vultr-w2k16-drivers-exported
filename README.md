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
