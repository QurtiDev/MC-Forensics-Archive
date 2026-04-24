# **$MFT (Master File Table)**
The Master File Table (MFT) is the backbone of NTFS file systems. It acts as a database of every file and folder, storing metadata for both existing and deleted files. Every action involving a file—creation, modification, movement, access, or deletion—results in updates to the MFT. Even after a file is deleted, its MFT record often remains until overwritten, making it an invaluable forensic artifact.

**MFT Structure and Attributes**
Each MFT entry consists of multiple attributes, the most important being:
- STANDARD_INFORMATION (0x10)
*Contains primary timestamps:*
- Created
- Modified
- Accessed
- Entry Modified

*FILE_NAME (0x30)*
Stores the filename and an independent set of timestamps. These timestamps may differ from STANDARD_INFORMATION and can reveal renaming or moving activity.

*DATA (0x80)*
- Points to the physical location of file content on disk.

**Accessing the MFT**
The MFT cannot be viewed through Windows Explorer. Specialized tools are required, such as:
- MFTECmd (Eric Zimmerman)
- FTK Imager

These tools allow investigators to:
- Analyze active files
- Recover evidence of deleted files
- Build accurate timelines of file activity
- Cross-referencing MFT data with Prefetch, registry artifacts, and event logs provides a highly reliable reconstruction of user behavior.







**Example: Suspicious DLL Loaded into csrss.exe**
It is not uncommon to discover suspicious DLLs loaded into critical processes such as csrss.exe. These DLLs may be unsigned or oddly named, yet no injector is immediately visible.
This is where the MFT becomes critical.
Investigation Process
Dump the MFT using MFTECmd:
MFTECmd.exe -f C:\$MFT --csv .

Search the resulting CSV for the DLL name
Examine Last Accessed timestamps, specifically:
FILE_NAME attribute (0x30)
This timestamp often reflects the moment the DLL was accessed or injected.
An alternative tool is Everything Search, which can quickly display last accessed times for files still present on disk, providing additional confirmation of injection timing.

Source
13Cubed – $MFT Forensics
https://www.youtube.com/watch?v=_qElVZJqlGY&t=275s




