### 📺 Presentation Clip
> Tool showcase here : https://youtu.be/tdGmnBJY-g4

### ⚙️ Interface & Key Features

* **Main Dashboard:**
    * **Search Bar:** Instantly filter tasks by name.
 **8 Quick Filters (Toggle Buttons):**
>         * 🔴 **Suspicious:** Tasks running cmd, powershell, rundll32, etc.
>         * 👤 **User Author:** Tasks authored by local users.
>         * 🚫 **Unsigned:** Missing digital signatures.
>         * 🔑 **LogOn:** Auto-run at user login.
>         * 📝 **Yara:** YARA rule matches present.
>         * 💬 **Args:** Command-line arguments present.
>         * 👻 **Registry:** Ghost tasks (registry/filesystem mismatch).
>         * 🐛 **IFEO:** IFEO debugger hijacks.
* **Real-Time Journal Scanning:** Flags tasks/executables modified **since boot** (highlights bypass attempts).
* **Task Details Panel:** Double-click any row for full analysis (signatures, YARA matches, IFEO hijacks, journal history).
‎ 
### 🛡️ Detection Capabilities

### **YARA Rule Engine:**
**19 custom rules** detecting cheats:
* Generic A-Series (3): Autoclicker detection.
* Generic B-Series (7): Packer/protection detection.
* Generic F-Series (7): Advanced packed executables.
* Generic G-Series (4): Injector patterns.
* Specific A-B: Targeted cheat detection.

### **Advanced Checks:**
* **Ghost Tasks:** Detects registry/XML mismatches used to hide persistence.
* **IFEO Hijacking:** Identifies debugger redirects (Image File Execution Options).
* **Signature Verification:** Classifies as **SIGNED / FAKE / CHEAT / UNSIGNED / NOT FOUND**.

### 🚀 Technical Optimizations

* **Tri-Source Validation:** Cross-references filesystem + registry + Journal to catch hidden and deleted/modifided tasks.
* **NTFS Journal Integration:** Detects post-boot modifications.
* **Multi-threaded Scanning:** Near-instant enumeration and analysis.

**Tool download Link:** https://github.com/ItzIceHere/RedLotus-Task-Sentinel/releases/download/RL/RedLotusTaskSentinel.exe

