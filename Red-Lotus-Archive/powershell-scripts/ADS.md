Steps - Basic
(1) Download AlternateStreamView and run it from the disk drive (Specify path c:\ for exmaple)
(2) Sort by date accessed or changed or file sizes
(3) Export ADS. Cheat ads are often over 5kmbs large but you'll get the gist.
https://www.nirsoft.net/utils/alternate_data_streams.html
Steps - Advanced:
(1) Extract file paths using regex `^([a-zA-Z]:\\.+)\\?$` in System Informer (use services like Explorer, SearchIndexer, Csrss high or low bytes)
(2) Save `Paths `into notepad
(3) Open Powershell ISE and run this command:

```powershell
$file = Read-Host "Provide txts of SearchIndexer or Csrss or Explorer"
if (-not (Test-Path $file -PathType Leaf)) {
    Write-Host "Unidentified"
    exit
}
Get-Content $file | ForEach-Object {
    $line = $_.Trim()
    if ($line -match "^([a-zA-Z]:\\.+)\\?$") {
        $path = $Matches[1]
        if ($path.EndsWith(":")) {
            Write-Host "Potential ADS in: $path"
            $parentDirectory = Split-Path $path -Parent
            Write-Host ("Results of 'dir /a' for $parentDirectory`:")
            Push-Location $parentDirectory
            Get-ChildItem -Force | ForEach-Object {
                $_.FullName
            }
            Pop-Location
            Write-Host
        }
    }
}```

Paste path to the .txt you extracted in step 1 
(4) To extract ADS that are still on the PC, use FTK Imager, navigate to the directory and copy file to elsewhere & rename it to .exe then run it. Or use alternatestreamview to extract it

(5) If the file isn't detected, means it's deleted, use USN Journal and filter the name of the ADS itself, that'll show its deletion date.
Steps will be discussed in webinars, no videos will be provided! - but here's a screenshot of it working 😄


