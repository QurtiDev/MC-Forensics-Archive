💻 Service Checker Script (PowerShell)

This little script lets you quickly check the status of important Windows services — super handy for troubleshooting or system maintenance.

🧩 What it does:

Checks a list of key Windows services (like SysMain, PCA, Schedule, Dcom, etc.)

Shows their display name and whether they’re Running or Stopped

If a service isn’t found, it’ll say “Not Found” instead of throwing an error

⚙️ How to use it:

Open PowerShell (run as Administrator for best results)

Copy and paste the script in

Hit Enter

```$services = @("SysMain", "PcaSvc", "DPS", "EventLog", "Schedule", "Bam", "Dusmsvc", "Appinfo", "SSDPSRV", "CDPSvc", "DcomLaunch", "PlugPlay")
$serviceTable = foreach ($service in $services) {
$status = Get-Service -Name $service -ErrorAction SilentlyContinue
[PSCustomObject]@{
'Service' = $service
'Full Name' = if ($status) { $status.DisplayName } else { "Not Found" }
'Status' = if ($status -and $status.Status -eq "Running") { "Running" } else { "Stopped" }
}
}
$serviceTable | Format-Table -AutoSize```

