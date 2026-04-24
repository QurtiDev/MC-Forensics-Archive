Prefetch
Prefetch is a core Windows performance and forensic artifact designed to speed up application startup while simultaneously leaving behind extremely valuable execution evidence. From a forensic perspective, Prefetch provides historical proof of program execution, process relationships, and loaded resources. On Windows systems where Prefetch is enabled, it becomes one of the most reliable artifacts for confirming whether a file has executed.
When an executable is launched, Windows creates a Prefetch file containing metadata about:

- The executable name
- The number of times it has been run
- The last execution time(s)
- Files and DLLs loaded during execution
- The execution path and environment

Prefetch also records causal execution, meaning processes that are spawned or triggered by other processes are logged as well. A common example is consent.exe, which is launched when an application requests administrative privileges through UAC. Even though the user may never directly launch consent.exe, it will still appear in Prefetch due to its relationship with the requesting executable.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------**Common Methods of Analyzing Prefetch**
There are multiple valid approaches to analyzing Prefetch artifacts, each serving a different investigative purpose:
- Win + R → prefetch
*This is a limited method, BUT it can prove useful!*

**WinPrefetchView (NirSoft)**
This is one of the most useful tools for detailed Prefetch analysis. It parses .pf files and displays:
- Execution count
- Last run times
- Full list of loaded files (DLLs, configuration files, etc.)

**PECmd (Eric Zimmerman)**
PECmd is a professional-grade forensic parser that can extract Prefetch data into structured output formats (CSV, JSON). It is especially useful when building timelines or correlating execution evidence with other artifacts.

**Location and Format**
Prefetch files are stored in:
*C:\Windows\Prefetch*

Each file uses the .pf extension and follows a naming format similar to:
PROGRAMNAME.EXE-<HASH>.pf

*The hash is generated based on the file path and helps differentiate identical filenames executed from different locations.*

**Executable vs Non-Executable Files**
A common misunderstanding in Prefetch forensics is the assumption that only .exe files are relevant. While it is true that Prefetch files are generated for executables, this does not mean other file types are irrelevant. 

DLL files cannot execute on their own and must be loaded into a host process. This means that when a DLL is injected or loaded maliciously, it will appear under the Prefetch entry of the injecting executable (e.g., regsvr32.exe, mavinject.exe, or a custom injector).
JAR files are executed through java.exe, which means Prefetch will log a java.exe entry rather than the .jar file itself.



---------------------------------------------------------------------------------------------------------------------------------------------------------------------------Using WinPrefetchView, investigators can examine the loaded file list inside a Prefetch entry to identify suspicious DLLs, configuration files, or cheat modules that were loaded during execution.
For example:
*A regsvr32.exe Prefetch entry loading a non-system DLL*
*A mavinject.exe entry referencing a cheat DLL*
*A java.exe entry loading a suspicious .jar file*
These scenarios strongly indicate abuse or malicious behavior.

**Example 1: Renamed Extension Logging in Prefetch**
A common evasion attempt involves renaming an executable file to a non-standard extension (e.g., .rpf) in an attempt to bypass detection.
*Question:*
Will a renamed executable still be logged in Prefetch?
Answer: Yes.
Windows identifies executables based on their PE structure, not just their extension. If an executable is renamed from Cheat.exe to Cheat.rpf but still retains executable characteristics, it will generate a Prefetch file.

However, the Prefetch entry will be named after the renamed file:
CHEAT.RPF-<HASH>.pf

This proves that:
Renaming extensions does not prevent Prefetch logging
Execution can still be proven even when users attempt to hide malicious tools

-------------------------------------------------------------------------------------------------------
*Example 2: File Executed, But Prefetch Shows an Old Timestamp*
Investigators may encounter situations where:

- Other artifacts clearly indicate recent execution
- Prefetch shows the last execution as days ago
- This discrepancy often indicates tampering.

*Common Causes*
- Manual deletion of Prefetch files
- Setting Prefetch files to read-only, preventing updates
- Copying old Prefetch files back into the directory

**Detection Method**
The first step is to use JournalTrace, which analyzes the NTFS USN Journal. By searching for:
- .pf
- The specific executable name

Investigators can identify:
- File Deletion events (deleted Prefetch files)

- Security Change events (read-only attribute changes)

- This allows confirmation that the suspect attempted to manipulate Prefetch artifacts to hide execution activity.

Sources;
https://www.dfir.training/artifact/win-os/prefetch 
https://www.youtube.com/watch?v=B4SmfKkazXo&t=15s
https://www.youtube.com/watch?v=xAE7fSGFcXM
discord.gg/redlotus

