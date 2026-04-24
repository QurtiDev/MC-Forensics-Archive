Creates an **HTML** showing **digital signatures** and **Replace** flags.
- If a row shows **Replace = true**, **double-click** it in the report to view more details.
- Commonly used for **DiagTrack** & **CSRSS** investigations.

**📦 Prep (with System Informer)**
1) Export/save target paths from **System Informer** to a `.txt`.
2) Name the file **exactly** one of the following (any works):
   - `p`
   - `paths`
   - `Search Results`
3) Open **CMD** or **PowerShell**, `cd` to the folder containing that `.txt`.

**▶️ Run (one line; works in CMD or PowerShell)**
powershell Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass && powershell Invoke-Expression (Invoke-RestMethod https://raw.githubusercontent.com/spokwn/powershells/refs/heads/main/signatures.ps1)

**📝 Output**
- Generates an **HTML** report with per-file **signature status** and **Replace** indicator.
- Double-click rows with **Replace = true** for extra context.


