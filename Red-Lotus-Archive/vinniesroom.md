https://start.me/p/m60j2v/digital-forensics
https://start.me/p/q6mw4Q/forensics
https://github.com/monnappa22/HollowFind
https://github.com/digitalsleuth/win-for
https://start.me/p/q6mw4Q/forensics
https://www.imageforensic.org/submit/
https://usbdetective.com/
https://volatility-labs.blogspot.com/2023/03/memory-forensics-r-d-illustrated-detecting-hidden-windows-services.html
https://www.sapien.com/software/sapien_free_tools
https://www.stark4n6.com/2023/03/introducing-sqlitewalker.html
https://github.com/mdegrazia/KAPE_Tools/issues/2
https://github.com/AndrewRathbun/KAPE-EZToolsAncillaryUpdater
https://www.oracle.com/database/technologies/instant-client/precompiler-downloads.html
https://www.elastic.co/security-labs/get-injectedthreadex-detection-thread-creation-trampolines
https://learn.microsoft.com/en-us/sysinternals/downloads/vmmap
https://petoolse.github.io/petools/
https://github.com/tclahr/uac
https://www.champlain.edu/Documents/LCDI/ApplicationAnalysis_S17.pdf
https://abrignoni.blogspot.com/2020/08/update-on-discord-forensic-artifacts.html
https://abrignoni.blogspot.com/2018/03/finding-discord-app-chats-in-windows.html
https://github.com/volatilityfoundation/volatility/wiki/Command-Reference
https://github.com/log2timeline/plaso/releases/tag/20221229
https://www.brimdata.io/
https://github.com/sumeshi/ntfsdump
https://andreafortuna.org/2018/10/01/accessing-volume-shadow-copies-within-a-forensic-image/
https://www.sans.org/tools/sift-workstation/
https://www.autopsy.com/download/
https://lolbas-project.github.io/






1. Task Scheduler
2. Virtual Mounts / Drives
3. Multi Purpose Analysis

**Registry Explorer, Journal, SYSInformer, Prefetch & TASK Scheduler**
> This webinar lasted for a while - I discussed latest Scheduler-related bypasses (that will not be posted) and recommended a logic of their detections:
> 1) MMC.EXE in prefetch on startup - if it includes task scheduler, assume the user has used it.
> 2) AntiSchedules will find tasks that are NOT deleted but are still on the system. It will evaluate the entropy of scheduled files (unless they include unicode) - if it includes unicode, use `regex:[^\x00-\x7FFFFFFF]` in search everything, proving its execution then is easy **or:**
> 3) Check Journal for deleted tasks, check Scheduler service in system informer for <command string to load all tasks **even if they were deleted from registry or just the file itself**, you can attempt using previousfilerecovery to try recovering latest deletions (although this VERY rarely works)
> 4) Use Registry Explorer for tasks cache, not only does it show deletions with dates, **BUT ALSO CONTENTS WITH UNICODE!**
> 5) Ban for whatever results / cheats found. Also having just CMD and Powershell / Powershell_ise scheduled can be deemed bannable if it was set by the user (use reg explorer as shown in the video to determine who set up the task) as we've discussed several bypasses in the webinar about these too. Details shared with only RL Course members 🙂
https://youtu.be/QTwTogXD3dM


**Registry Explorer & Virtual Mounts / Drives**
> As discussed in the webinar, Reg Explorer with USBStor, Volumeinfocache and so on can be used to identify USB Traces, prefetch can log direct executions from other drives under `Volume.` **which means an unidentified drive letter, therefore - dismounted**, we can use Reg Explorer with `CTRL+F` function to find the drive letters. *More in-depth preview of drive related detections will be discussed in upcoming webinars*
`The video also includes a comparison of using registry hives themselves from C:\Windows\system32\config and Reg Explorer - where you can see how some data can be immediately lost or not immediately logged while analyzing the hive files themselves.` *More in-depth discussions regarding raw hive usages will be discussed in future webinars*
https://youtu.be/QR8A6Fh--N4

## WEEK 1

- One of the things we discussed in the previous seminar was **MPLog**, - Windows Antivirus Logs that can not only log `Assigning / removing / changing signatures`, but also what applications did the antivirus skip scanning on, what applications it scanned, what applications it detected (under MPDetections) and so on.
> 🗒️ | Here is where to find it manually and an automated .csv converting script. 
https://gist.github.com/Qazeer/5ad40f6e98362520290d13f3015f79ec

## DEMO:
> https://youtu.be/qu9SUo6SKYA


Tool: https://github.com/lattiahirvio/SSTool/tree/main
Guide: https://docs.google.com/document/d/1UDPuSxJqv2p-JKrQlGRjiI5ugk2GCaD6VdYvLI4oQp8/edit
SPANISH: https://docs.google.com/document/d/1NwoS6SXm39PLEQ5EjxWUkhiwVcWzeFj-9xgRjgdnZa4/edit

```
Not Contains([Message], '.jar') And Not Contains([Message], '.rar') And Not Contains([Message], '.bat') And Not Contains([Message], '.zip') And Contains([Message], 'webfile:')

Contains([Message], 'lofi/sample/expensive:') And Not (Contains([Message], '.jar') Or Contains([Message], '.rar') Or Contains([Message], '.bat') Or Contains([Message], '.zip') Or Contains([Message], '.ps1') Or Contains([Message], '.tmp') Or Contains([Message], '.pyd') Or Contains([Message], '.dll') Or Contains([Message], '.js') Or Contains([Message], '.cmd') Or Contains([Message], '.sys') Or Contains([Message], '.yar') Or Contains([Message], '.yml'))
NOTE: Consider removing the .dll one however be warned there will be a lot of spam dll’s.

Contains([Message], 'First scan on a volume:') And EndsWith([Message], '.exe') Or Contains([Message], 'regsvr32.exe') Or Contains([Message], 'https://')

Contains([Message], 'TaintReason:') And Not Contains([Message], 'n/a')
NOTE: Can also search javaw.exe which could show injections directly into mc. For example, Vape shows up with this method often.

Contains([Message], '*************RTP Perf Log*******************')
Copy and paste to notepad and ctrl F for .exe    
```
@everyone 

# `Services Agreement and Waiver`

**Services Agreement**: This is the agreement that outlines the rules and expectations for using our services. It covers what you can expect from us, what we expect from you, details about payments, and the scope of the services provided. By purchasing a service, you agree to these terms.

**Waiver**: This is a document where you acknowledge and accept certain risks involved with the digital forensic and screensharing services. It confirms that you understand the nature of the coaching and agree to release Red Lotus from liability for specific potential outcomes that may arise during the sessions.

https://docs.google.com/document/d/1gkyBgcHdEn3GyJyABtx89zQtyKosj45shu23p9hKQp8/edit?usp=sharing
https://docs.google.com/document/d/1ydgSRVrbbeyvjUlAcMK32GjoaSjHPwJewifTehNLNTg/edit?usp=sharing




https://github.com/danielbohannon/Invoke-DOSfuscation


https://www.wietzebeukema.nl/blog/bypassing-detections-with-command-line-obfuscation


