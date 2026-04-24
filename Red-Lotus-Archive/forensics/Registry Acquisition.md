# Registry Acquisition <@&1298026862521352263> (Using Zimmerman Tools)

Run the .BAT to gather some stuff from Registry as a .csv!

-# You can modify / update the .bat itself as well.
```bat
@echo off

:: Step 1: Download RECmd.zip
echo Downloading RECmd.zip...
powershell -Command "Invoke-WebRequest -Uri https://download.ericzimmermanstools.com/net6/RECmd.zip -OutFile RECmd.zip"

:: Check if the download was successful
if not exist RECmd.zip (
    echo Failed to download RECmd.zip. Exiting.
    exit /b 1
)

:: Step 2: Unzip RECmd.zip
echo Unzipping RECmd.zip...
powershell -Command "Expand-Archive -Path RECmd.zip -DestinationPath . -Force"

:: Check if the unzipping was successful
if not exist RECmd (
    echo Failed to unzip RECmd.zip. Exiting.
    exit /b 1
)

:: Step 3: Change directory to RECmd folder
cd RECmd

:: Step 4: Run the specified RECmd command
echo Running RECmd.exe with the specified arguments...
recmd.exe -d C:\Windows\System32\config --bn batchexamples\dfirbatch.reb --csv .\
recmd.exe -d C:\Windows\System32\config --bn batchexamples\Kroll_Batch.reb --csv .\
recmd.exe -d C:\Windows\System32\config --bn batchexamples\RECmd_Batch_MC.reb --csv .\
recmd.exe -d C:\Windows\System32\config --bn batchexamples\RegistryASEPs.reb --csv .\
recmd.exe -d C:\Windows\System32\config --bn batchexamples\SoftwareASEPs.reb --csv .\
recmd.exe -d C:\Windows\System32\config --bn batchexamples\AllRegExecutablesFoundorRun.reb --csv .\
recmd.exe -d C:\Windows\System32\config --bn batchexamples\SoftwareWoW6432ASEPs.reb --csv .\
recmd.exe -d C:\Windows\System32\config --bn batchexamples\BatchExampleWildCard.reb --csv .\
recmd.exe -d C:\Windows\System32\config --bn batchexamples\UserActivity.reb --csv .\

:: End of script
echo Script completed.
pause```


