# 📂 MFTECmd 

## 🔹 Introduction
**MFTECmd** is part of *Eric Zimmerman’s Tools*, designed to parse the **Master File Table (MFT)** and related NTFS artifacts.  
It helps forensic investigators analyze file system activity, including file creation, modification, access, renaming, and deletion.

---

## ⚙️ Useful Commands

### 🔎 Parse the Journal ($UsnJrnl)
`MFTECmd.exe -f C:$Extend$UsnJrnl:$J -m C:$MFT --csv .`

- Works like **JournalTool** and **JournalTrace**  
- Columns worth filtering:  
  - 📂 **Parent Path** → useful for deleted scheduled task detections  
  - 📝 **Extension**  
  - 🔄 **Update Reason**  
  - ⏱️ **Update Timestamp**  
- Replace `C:` with another drive letter to analyze other volumes.

---

### 📑 Parse the MFT
`MFTECmd.exe --at -f C:$MFT --csv .`

- Parses the `$MFT` of the C drive  
- Filter for:
  - **zone.identifier** (useful for downloaded file checks)  
  - Timestamps from **0x10** and **0x30** attributes for deeper investigation

---

## 🕵️ Example Use
- Detect deleted scheduled tasks via **Parent Path** filtering  
- Track downloaded files by **zone.identifier**  
- Correlate timestamps to reconstruct user activity even when files are gone  

---

## ✅ Tips
- MFTECmd isn’t limited to `$J` and `$MFT` – experiment with different inputs  
- Always export to **CSV** for easy filtering in Excel or **Timeline Explorer**  
- Cross-reference timestamps for strong forensic evidence  

---

## 📌 Conclusion
**MFTECmd** is an essential NTFS forensic parser.  
By analyzing `$MFT` and `$UsnJrnl`, investigators can uncover hidden file activity, detect deleted tasks, and reconstruct a timeline of user actions across drives.

Download link: https://ericzimmerman.github.io/#!index.md
