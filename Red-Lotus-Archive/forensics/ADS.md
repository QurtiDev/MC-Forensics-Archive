1. **Obtain the Tool**

   * Download **AlternateStreamView** from Nirsoft:
     🔗 https://www.nirsoft.net/utils/alternate\_data\_streams.html
   * Launch it and specify a drive to scan (e.g., `C:\`).

2. **Analyze the Results**

   * Sort results by **Last Accessed**, **Modified Date**, or **Stream Size**.

3. **Export Findings**

   * Save or export identified ADS entries for review.
   * **Note:** Suspicious or malicious streams are often **larger than 5 MB**, but context matters.

1. **Collect File Paths via System Informer**

   * Use regex `^([a-zA-Z]:\\.+)\\?$` to extract paths from processes such as:

     * `Explorer`
     * `SearchIndexer`
     * `Csrss`
   * Export captured file paths to a `.txt` file for analysis.

2. **Run PowerShell Analysis**
   * Open **PowerShell ISE** and execute the following script:
```powershell
Script Attached
```

* When prompted, provide the `.txt` file path created earlier.

4. **Extract ADS Artifacts**

   * If streams are still present on disk:

     * Use **FTK Imager** to browse the directory, copy the file, rename to `.exe`, and test execution.
     * Or re-use **AlternateStreamView** to extract the ADS directly.
   * If no stream is found, check the **USN Journal** for entries matching the ADS name.
   * This reveals deletion events, timestamps, and related metadata.

```powershell
$file = Read-Host "Enter path to the .txt file from System Informer"
if (-not (Test-Path $file -PathType Leaf)) {
    Write-Host "File not found or invalid."
    exit
}

Get-Content $file | ForEach-Object {
    $line = $_.Trim()
    if ($line -match "^([a-zA-Z]:\\.+)\\?$") {
        $path = $Matches[1]

        # Check if the path is valid and points to a file
        if (Test-Path $path -PathType Leaf) {
            Write-Host "`n[+] Checking file: $path"

            try {
                $streams = Get-Item -LiteralPath $path -Stream * -ErrorAction Stop
                if ($streams.Count -gt 1) {
                    Write-Host "    Found ADS:"
                    $streams | ForEach-Object {
                        if ($_.Stream -ne "::$DATA") {
                            Write-Host ("     - {0} ({1} bytes)" -f $_.Stream, $_.Length)
                        }
                    }
                }
                else {
                    Write-Host "    No ADS detected."
                }
            }
            catch {
                Write-Host "    Access denied or unable to read file."
            }
        }
        elseif (Test-Path $path -PathType Container) {
            Write-Host "`n[?] Path is a directory, skipping: $path"
        }
        else {
            Write-Host "`n[-] Path not valid: $path"
        }
    }
}
```


