**📺 Presentation Clip**
Quick tool showcase here: https://youtu.be/WzYlw8FagrA
![alt text](image.png)

**⚙️ Interface (GUI)**
- MEMORY SCAN: Automatically detects the running javaw.exe process and scans the mods currently loaded in memory.
- DISK SCAN: Allows you to manually select a specific mods folder from your disk to scan for threats.

**🛠️ Features**
- Dashboard: The central hub for managing scan results.
- Search & Filter: Instantly filter by Mod Name or toggle views for Unverified, Not Found, or Detected mods.
- Smart Alerts: Visual warnings (⚠) if the mods folder was modified after the game started, alerting you to potential "self-destruct" or "hide" tactics.
- Download Source: Automatically detects and displays the origin URL (e.g., CurseForge, Modrinth) for each mod.
- Mod Details: Double-click any row to open a detailed popup containing the file hash, full path, and deep analysis data.
- **USN Journal Monitoring**: Advanced filesystem tracking that detects:
  - **Deleted/Moved Mods**: Files removed or moved out of the folder appear as "MOD NOT FOUND" entries in red
  - **Modified Mods**: Files altered during runtime are highlighted in **bold orange** (both name and path)
  - **Detailed Logs**: View a complete timeline of file events (Create, Delete, Move/Rename, Modify) with precise timestamps in the Mod Details popup
  - **Smart Filtering**: Journal checks only show modifications that occurred after Minecraft started (Memory Scan) or after system boot (Disk Scan), preventing false positives from old changes
  - **Bypass Detection**: Catches the many ways to unload, remove, and modify a mod after it has been used.

‎ **
🛡️ Advanced Detection Capabilities**
The Dynamic Detection Engine analyzes raw bytecode directly from memory. 
I have analyzed over 800 cheat packages to calibrate the detection logic:

- Combat Modules: 175+ unique signatures for detecting KillAura, Velocity, Reach, and AutoClicker patterns.
- Structural Fingerprints: 47+ unique patterns identifying hidden "Module Managers", and known cheat architectures.
- Obfuscation Analysis: Detects heavy obfuscation (e.g., >30% single-letter classes) and flow obfuscation often used to hide illegitimate code.
- Native Injection: Flags suspicious JNI injection vectors and unauthorized native libraries (.dll/.so) hidden within JARs.

**🚀 Technical Optimizations**
Implemented to ensure maximum performance and stability:
- In-Memory Analysis: Uses miniz to decompress and analyze JAR files directly in RAM. This eliminates temporary files, resolves permission issues, and makes scanning 10x-50x faster.
- Parallel Scanning: Utilizes multithreading to analyze multiple mods simultaneously, scaling linearly with your CPU cores.
- Smart Caching: Implements a transient cache to provide instant results for files that haven't changed since the last scan.

**Tool Download Link**: https://github.com/ItzIceHere/RedLotus-Mod-Analyzer/releases/download/RL/RedLotusModAnalyzer.exe

