# Mod Analyzer
-#  By <@930191705360195665> to RedLotus

It verifies the integrity of Minecraft mods by comparing their file hashes against Modrinth’s API and a custom database of mods not available on Modrinth. Additionally, it scans mods and their dependency jars for common cheat strings and uses Zone.Identifier to determine the original download source.

-# Note: This script is supposed to speed up the mod analysis process by identifying verified mods. Unknown mods still need to be reviewed manually.

```ps1
powershell Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass && powershell Invoke-Expression (Invoke-RestMethod https://raw.githubusercontent.com/HadronCollision/PowershellScripts/refs/heads/main/HabibiModAnalyzer.ps1)
```


