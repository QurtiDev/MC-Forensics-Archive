# 🗂️ RECmd

## 🔹 Introduction
**RECmd** is the command-line version of *Registry Explorer* from Eric Zimmerman’s EZ Tools.  
It parses **Windows Registry hives** to extract keys, values, and timestamps — crucial for user activity and persistence analysis.

---

## 🎯 What It Reveals
- 🔑 Registry keys and values (from SYSTEM, SOFTWARE, NTUSER.DAT, etc.)  
- ⏱️ Last written timestamps for keys  
- 🛠️ Persistence mechanisms (Run keys, Services, BAM/DAM, etc.)  
- 📂 User activity (recent docs, shellbags, typed paths)

---

## ⚙️ Useful Commands
```bash
# Parse a registry hive into CSV
RECmd.exe -f "C:\Users\Alice\NTUSER.DAT" --csv .\Output

# Use a batch file with pre-built queries
RECmd.exe --bn Queries\RecentDocs.reb -f "C:\Users\Alice\NTUSER.DAT" --csv .\Output

# Recursive parsing of a folder with hives
RECmd.exe -d "C:\Forensics\Hives" --csv .\Output
