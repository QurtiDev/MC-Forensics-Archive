# 📂 bstrings (Zimmerman Tools)

## 🔹 Introduction
**bstrings** is part of *Eric Zimmerman’s Tools*, built to improve on the traditional `strings` utility.  
While `strings.exe` extracts ASCII/Unicode text from binaries, **bstrings** goes further by adding **context, entropy analysis, and filtering**, making it much more useful in forensics and malware analysis.

---

## 🎯 Purpose
- 🧩 Extract both **ASCII and Unicode strings** from files  
- 🎚️ Use **entropy-based filtering** to remove noise  
- 🔎 Identify **URLs, IPs, registry paths, file paths, GUIDs, CLSIDs** and more  
- 📑 Export results to CSV/JSON for deeper analysis

---

## ⚙️ Useful Commands

## 🕵️ Detecting Cleared BAM
The **BAM (Background Activity Moderator)** registry key sometimes gets cleared by attackers to hide persistence.  
You can still detect traces using **bstrings**:

### 🔹 Step 1: Download
Grab **bstrings.exe** from Eric Zimmerman’s GitHub or via the EZ Tools package.

### 🔹 Step 2: Run Command
`bstrings.exe -f "C:\Windows\system32\config\SYSTEM" --ls harddiskvolume`

`bstrings.exe -f "C:\Windows\system32\config\SYSTEM" --ls harddiskvolume -o .\Output.txt`

(use second one If you want it to output to text file)

Download link: https://ericzimmerman.github.io/#!index.md


