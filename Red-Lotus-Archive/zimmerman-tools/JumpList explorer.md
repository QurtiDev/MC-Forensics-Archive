# 📂 JumpList Explorer 

## 🔹 Introduction
**JumpList Explorer** is part of *Eric Zimmerman’s Tools* a free set of forensic utilities used in **Digital Forensics and Incident Response (DFIR)**.  
Windows *Jump Lists* track recently accessed files and applications, making them valuable for investigators.

---

## 🎯 Purpose
- Parse **Jump List files**: `.automaticDestinations-ms` & `.customDestinations-ms`
- Extract:
  - 📁 File paths  
  - ⏱️ Timestamps (created, modified, accessed)  
  - 🆔 Application identifiers (AppID)  
- Present the data in a clear, human-readable format

---

## ⚙️ How It Works
1. **Input** → Collect Jump List files from:
`C:\Users<username>\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations`
`C:\Users<username>\AppData\Roaming\Microsoft\Windows\Recent\CustomDestinations\`

Download link: https://ericzimmerman.github.io/#!index.md