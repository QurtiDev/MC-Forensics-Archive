## Queries ® 
```powershell
reg query "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\bam\state\usersettings" /s
- Query BAM (Background Activity Moderator) for program execution history

reg query "HKCU\Software\Microsoft\Windows\CurrentVersion\Run"
- Autostart programs for current user

reg query "HKLM\Software\Microsoft\Windows\CurrentVersion\Run"
- Autostart programs for all users

reg query "HKLM\SYSTEM\CurrentControlSet\Enum\USBSTOR" /s
- Lists USB storage devices ever connected

reg query "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\UserAssist" /s
- Shows GUI-executed programs (ROT13 encoded)

reg query "HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache"
- ShimCache (AppCompatCache) program execution history
```
## Queries 2 
```c#
dir C:\Windows\Prefetch\*.pf
- Prefetch files – evidence of program execution

dir "C:\Users\<User>\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations"
- Jump Lists – recent documents and program usage

dir C:\$Recycle.Bin /s
- Shows deleted files and their original paths (Recycle Bin artifacts)

wevtutil qe Security /q:"*[System[(EventID=4624)]]" /f:text /c:5
- Show last 5 login events (4624 = login, 4634 = logout)

netstat -ano
- Active TCP/UDP connections with PIDs

arp -a
- Cached IP–MAC mappings (past local network connections)

ipconfig /displaydns
- DNS cache – recently resolved domains

schtasks /query /fo LIST /v
- Lists scheduled tasks (used for persistence by malware)
```

## Powershell
```powershell
Get-Content "C:\Windows\System32\LogFiles\Firewall\pfirewall.log" | Select-String "DROP"
- Parses firewall logs for dropped/allowed suspicious traffic
```


