Generates an **HTML report** from BAM data, including:
- **Last execution date**
- **Digital signatures**
- **Replace** status (if **Replace = true**, double-click the row in the report to see extra details)

**▶️ Run (CMD one line)**
```powershell Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass && powershell Invoke-Expression (Invoke-RestMethod https://raw.githubusercontent.com/spokwn/powershells/refs/heads/main/bamparser.ps1)```

**📝 Notes**
- The command works from **CMD** or **PowerShell** (it sets a *process-scope* policy bypass).
- After it finishes, open the **generated HTML** to review results.

