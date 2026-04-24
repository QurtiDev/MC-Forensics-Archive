**🧾 RL SIGNATURES CHECKER (Red Lotus)**
By **@Alekhine**  •

Checks the **digital signature (Authenticode)** of files listed in `paths.txt`.

**⚠️ Recommendation**
It’s recommended to use **Spok’s Paths Parser** first. Use this script **only if Spok’s tool doesn’t work**.

**📄 Prepare `paths.txt`**
- Create a file named **paths.txt** in the same folder you’ll run the command from.
- Put **one full file path per line**, wrapped in quotes:

  "C:\Windows\System32\notepad.exe"
  "C:\Users\YourUser\Downloads\app.exe"

**▶️ Run (CMD as Admin | works with PowerShell 3+)**
Paste this single line:
powershell Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass && powershell Invoke-Expression (Invoke-RestMethod https://raw.githubusercontent.com/bacanoicua/Screenshare/main/RedLotusSignatures.ps1)

**📝 Notes**
- Requires **Administrator** privileges.
- The script reads `paths.txt` in the current directory and outputs signature status for each path.
- Tip: **Ctrl+Shift+C** to copy all paths from your source list before pasting into `paths.txt`.

**🎥 Demo**
https://streamable.com/5wk2m3


