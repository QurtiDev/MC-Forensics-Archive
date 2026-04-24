### 🛡️ **RedLotus Bam Checker** 🕵️‍♂️




This PowerShell script is a super useful diagnostic and security tool. It analyzes your Windows execution history (the **BAM** registry key) to show you which programs have been launched on your PC, along with the exact time and date of their last execution.

As a bonus, it also checks the **digital signature** of these files. If a program is unsigned or has an invalid signature, it's a red flag ⚠️ that could point to malware or a cheat.



### **How to Use It:**

No need to download anything, it's super easy

1. **Open PowerShell as an Administrator**: Right-click on the Windows icon or in the search bar, then choose **"Windows PowerShell (Admin)"** or **"Terminal (Admin)"**.

2. **Copy and paste the command below** into the PowerShell window, then hit `Enter`:

`iex(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PureIntent/ScreenShare/main/RedLotusBam.ps1')`

3. **Let the script run.** It will scan your PC, and once it's done, a window will pop up with a table of all the applications that have been launched, their path, the time, and their signature status.

4. **Review the results.** If you see a program that is unsigned (Invalid Signature), it's important to figure out where it came from.



*I specify that it is preferable to use Bam Parser from Spokwn than this script <#1338621914213777489> *

