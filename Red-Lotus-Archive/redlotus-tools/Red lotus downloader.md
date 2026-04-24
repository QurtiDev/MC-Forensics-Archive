This tool is the central hub for all official tools approved by RedLotus.

## 📺 Presentation Clip
Quick tool showcase [here](https://youtu.be/RZC7H5V1plo)

### ⚙️ Interface & Features

The tool consists of **3 main tabs**:
1.  **Hub Tab**: Manually select the tool categories to download (Spok, Nirsoft, Zimmerman, Other).
2.  **Presets Tab** (Central): Download predefined file groups with a unified progress bar.
    * **Download All**: All tools from all categories.
    * **Quick SS**: Quick selection of essential tools.
    * **Full SS**: Full suite of tools.
3.  **Status Tab**: View the detailed progress of downloads started from the Hub Tab.

### 🔗 Quick Links (Footer)

Three quick buttons at the bottom:
* **Open Folder**: Opens the save folder for downloaded files (`C:\SS1`).
* **Discord**: Invitation to the official RedLotus Discord server.
* **Guides**: Opens the official RedLotus online guide.

> 📝 **Guide Utility**: Provides easy access to strings/commands/PowerShell scripts and increases **transparency** on how tools and scripts work (improving SSer/Player communication).

### 🚀 Technical Optimizations

Implemented to ensure better speed:
* **Multithreading (Parallel Downloads)**: Up to **4 simultaneous files** to drastically reduce overall times.
* **Connection Reuse (Keep-Alive)**: Keeps the connection to the server open, avoiding the overhead of constant reconnections for each file.
* **Increased Buffer (64KB)**: Uses a larger buffer (compared to the standard 8KB) to reduce CPU usage and disk I/O operations.

### 🛡️ Future Proof

The tool is built so that download links are **not hard-coded** within the executable itself, but are saved in an **online tool list**.
This allows us to **change, add, or remove** any tool from the download lists for every button in just a few seconds, and the current EXE will continue to function seamlessly with the update.

