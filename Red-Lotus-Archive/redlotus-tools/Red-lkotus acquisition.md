[**REDLOTUS ACQUISITION**](https://github.com/RedLotus-Development/RedLotus_Acquisition?tab=readme-ov-file)
‖ Extract **process dumps** and analyze **signed/unsigned** files.

**🛠️ What it does (stages)**
1) **Stage 1 — Memory Acquisition**
   - Dumps all *Administrative* process memories as `process.dmp` into `./ProcessDump/`.
2) **Break Option**
   - Press **CTRL+C** any time *after* Stage 1 to stop before continuing.
3) **Stage 2 — BSTRINGS Setup**
   - Automatically downloads and unzips Eric Zimmerman’s **bstrings**.
4) **Stage 3 — Path Extraction**
   - Parses dumped `process.dmp` files for **win_path** artifacts and writes results to **`paths.txt`**.
5) **Signature Verification**
   - After extraction, identified files are scanned for **digital signature** status.

**⏱ Duration**
~20 minutes for the full flow (varies by RAM/process count).

**📝 Notes**
- You can modify the script as needed.
- Tip: add the **silent** switch to `bstrings` to speed up path extraction.

**🔗 Used Utilities**
- BSTRINGS → https://ericzimmerman.github.io/#!index.md
- Timeline Explorer → https://ericzimmerman.github.io/#!index.md
- PowerShell 7 → https://learn.microsoft.com/en-us/shows/it-ops-talk/how-to-install-powershell-7

**🌐 REDLOTUS**
- 🎬 YouTube Demo: https://youtu.be/cIrdJHYtw4g

**👤 Credits**
Script by **Konstantine [UnMonsieur]**

