# How to locate entries in _Task Manager Startup_ tab

## Locating _Startup_ folder
1. Per-user  
  `%ProgramData%\Microsoft\Windows\Start Menu\Programs\Startup`
3. All users  
  `%Appdata%\Microsoft\Windows\Start Menu\Programs\Startup`

## Using _Autoruns_ tool 
"This utility, which has the most comprehensive knowledge of auto-starting locations of any startup monitor, shows you what programs are configured to run during system bootup or login, and when you start various built-in Windows applications like Internet Explorer, Explorer and media players. These programs and drivers include ones in your startup folder, Run, RunOnce, and other Registry keys." (Microsoft, 2022)  
- Downloading _Autoruns_ tool from Microsoft website;
- Runnning _Autoruns_ and then looking for the info under _Logon_ tab.  
🎺Note: Autoruns won’t display entries that are disabled in _Startup_ tab because they are stored in a different registry location.

## Locating in Registry (_regedit.exe_)
1. Per-user
  - `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Run`
  - `HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Run` - For 32-bit programs on a 64-bit Windows
  - `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\StartupApproved\Run` - For disabled entries in _Startup_ tab
2. All users
  - `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run`
  - `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Run`
  - `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\StartupApproved\Run`
  - `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\StartupApproved\Run32`    
🎺 Note: The disabled items in _Startup_ tab are stored in the `StartupApproved` registry locations.

### Reference: 
Srinivasan, Ramesh. How to Remove Invalid Entries from Task Manager Startup Tab. winhelponline.com. Retrieved from: https://www.winhelponline.com/blog/task-manager-startup-tab-entries-remove-invalid/

