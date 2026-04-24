```markdown
# 📎 LECmd (Zimmerman Tools)

## 🔹 Introduction
**LECmd** parses **Windows LNK (shortcut) files**.  
LNK files are automatically created when users open files or applications, and they store rich metadata about the target.

---

## 🎯 What It Reveals
- 📂 Original file path (including UNC/network paths)  
- ⏱️ File timestamps (creation, last modified, last access)  
- 💻 Machine info (MAC address, volume serial, netbios name)  
- 🔗 Can reveal deleted or moved files


## ⚙️ Useful Commands
```
# Parse a single LNK file
LECmd.exe -f "C:\Users\Alice\AppData\Roaming\Microsoft\Windows\Recent\doc1.lnk"

# Parse all LNK files in a folder
LECmd.exe -d "C:\Users\Alice\AppData\Roaming\Microsoft\Windows\Recent" --csv .\Output