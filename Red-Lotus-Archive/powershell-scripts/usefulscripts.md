# <:Headquarters:1169761468569374780> - `Powershell Scripts` __NEW__

```Following Scripts are authenticated and valid to be used in partner SS servers```


## 1. RL Collector [PS Edition]
- Run the RLCollector script in any directory and wait for the processing to finish.
- It will download and parse useful Zimmerman tools (As well as additionally copy and gather forensically useful artifacts)
`Alternatively you may create a .ps1 script and run it as a CLI version:`
```powershell
.\RLCollector.ps1 -WorkingDirectory "C:\Path\TO\Your\CSVS"
```

## 2. "Master Timeliner" (Aggregator)
- Run it in a folder which includes a lot of .csv files
- It will find all .csv files in sub-folders and sub-directories of the provided folder
- It will create a Timeline (one single .csv file combining all of the results) and output skipped .csvs
- **This best works with RLCollector and Tech's SS Collector since it also collects .csv evidences**
- Put results in Timeline Explorer.

## `by UnMonsieur / Konstantine`


