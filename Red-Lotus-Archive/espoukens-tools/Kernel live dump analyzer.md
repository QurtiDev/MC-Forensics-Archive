# 📊 Kernel Live Dump Analyzer

## 🔸  Introduction
**KernelLiveDumpTool** is a tool made by spokwn, made to analyze Kernel and Ram dumps.

## 💪 Capabilities
- **Shows DLL injections/loading via `regsvr32` or `rundll32` **
- **Indicators of Fileless Execution** 
- **File replacement methods** (like `echo` or `type`)
- **`forfiles` and `wmic` executions**
- **Deleted/modified registry keys via `reg` commands** (the command could be in CMD or PowerShell)

## ⚙️ How to use
- Create the Kernel dump file `.dmp` (if you're ram dumping then rename the ram dump to  `.dmp`)
- Place the the `.dmp` file in the same folder as the tool
- Run the Program, and then choose if you want to add custom keywords or not
- If you're doing a Ram dump the tool might not recognize it and you would need to put the full path of the `.dmp` file

Download link: https://github.com/spokwn/KernelLiveDumpTool


