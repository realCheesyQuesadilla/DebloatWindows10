# DebloatWindows10
#### Debloat Windows 10 with PowerShell
Use Window's tools against itself! While it doesn't debloat everything, it's a step in the right direction for getting rid of all the junk Windows 10 ships with.  

Comments are added to the code to tell you specifically what is being deleted. If you would like to keep something just simply comment out the following line of code or delete it.  

This script will need to be ran in administrator mode to delete some items. This can be done by hitting the windows key on your keyboard, typing in "PowerShell", right-clicking the "Windows PowerShell" icon, and clicking "Run as administrator".  

If you reserve an error containing "cannot be loaded because running scripts is disabled", you will need to change the execution policy. You can do this by typing 
```
Set-ExecutionPolicy remotesigned
```
After running this script you can set it back to the original by typing
```
Set-ExecutionPolicy restricted
```

#### Reload Windows 10 Defaults
If you found this script removed too many programs, simply run 
```
Get-AppxPackage -AllUsers| Foreach {Add-AppxPackage -DisableDevelopmentMode -Register “$($_.InstallLocation)\AppXManifest.xml”}
```
To download all of the default programs and add them back. This may take awhile.
