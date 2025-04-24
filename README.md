# Windows-VM-AppCleanup
Powershells command to remove default app that are installed by default when you create a new windows10 or 11 vm.
If you need a quick clean Windows vm without the default useless application that nobody like.
This is very usefull.

## How to use
```
1. Run PowerShell as admin.
2. cd c:\path\to\cleanup.ps1
3. .\cleanup.ps1
```

## Optional
```
You can list the installed apps by copy/paste the following:
For Microsoft apps:
DISM /Online /Get-ProvisionedAppxPackages | select-string Packagename

For an extended list:
Get-AppxPackage | ft Name, PackageFullName -AutoSize

Universal Commands
Uninstall all apps ( NOT RECOMMENDED ):
Get-AppxPackage -allusers | Remove-AppxPackage

Reinstall all default apps:
Get-AppxPackage -AllUsers| Foreach {Add-AppxPackage -DisableDevelopmentMode -Register “$($_.InstallLocation)\AppXManifest.xml”}
```
