# Introduction <@&1298026862521352263> 
```HeapLeakDetection is a forensic artifact associated with Windows RADAR—the Resource Exhaustion Detection and Resolution system built into Windows. Essentially, when Windows detects that an application is consuming an unusually large amount of memory (suggestive of a memory leak), it logs details about that event in the registry under a key such as:
[ HKLM\Software\Microsoft\RADAR\HeapLeakDetection\DiagnosedApplications ]```

**Forensic Artifact**
The Memory Leak Diagnoser is triggered every TimerInverval minutes. When triggered, it gets a list of all running processes, and sorts them by their amount of committed memory (in descending order). 


In order to detect and analyze this NEW Evidence of Execution Artifact, we can use MHagis' Github Tool:
 https://github.com/MHaggis/HeapLeakDetection/releases


Original Source
https://x.com/samaritan_o/status/1848743680384889031/photo/1

