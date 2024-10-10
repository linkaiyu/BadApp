# BadApp
test app crash for debugging

1. download procdump from https://learn.microsoft.com/en-us/sysinternals/downloads/procdump
2. unzip the files to where you'd like store the dump files, e.g. c:\dumps
3. start a command with Administrator, execute this command to set it as JIT debugger:

C:\dumps>procdump -i c:\dumps -ma

you will see the following output: 

ProcDump v11.0 - Sysinternals process dump utility
Copyright (C) 2009-2022 Mark Russinovich and Andrew Richards
Sysinternals - www.sysinternals.com

Set to:
  HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug
    (REG_SZ) Auto     = 1
    (REG_SZ) Debugger = "C:\dumps\procdump.exe" -accepteula -ma -j "c:\dumps" %ld %ld %p

Set to:
  HKLM\SOFTWARE\Wow6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug
    (REG_SZ) Auto     = 1
    (REG_SZ) Debugger = "C:\dumps\procdump.exe" -accepteula -ma -j "c:\dumps" %ld %ld %p

ProcDump is now set as the Just-in-time (AeDebug) debugger.

4. you can now start the BadApp to test. Click Help | About | OK to crash the app. You should see dump files in c:\dumps\BadAppxxx.dmp

5. to uninstall, type procdump -u
6. Note: if leave uninstalled, ProcDump will keep capturing crash dumps to the folder whenever an app crashes on your machine. So keep monitoring your c:\dumps folder

