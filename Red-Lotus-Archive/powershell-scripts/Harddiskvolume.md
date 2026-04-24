- A powershell script to check DPS harddiskvolume paths to show us the real paths with the drives included.

Usage;
- Open system informer as admin and turn on kerneldrive mode.

- Dump DPS service with harddiskvolume.

- Paste into notepad.

- Save the .txt file as **paths.txt**.

- Open cmd as admin CD into directory and paste it.

- Watch the magic happen.

```
powershell Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass && powershell Invoke-Expression (Invoke-RestMethod https://raw.githubusercontent.com/bacanoicua/Screenshare/main/RedLotusHardDiskVolumeConverter.ps1)
```


