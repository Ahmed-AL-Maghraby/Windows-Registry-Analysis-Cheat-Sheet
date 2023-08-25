# Windows Registry Analysis Cheat Sheet

<br>
<br>
https://github.com/Ahmed-AL-Maghraby/Windows-Registry-Analysis-Cheat-Sheet/tree/main#system-info-and-accounts
## Table of Contents

<br>

| Table of Contents |
| -------------------- |
| [System info and accounts](https://github.com/Ahmed-AL-Maghraby/Windows-Registry-Analysis-Cheat-Sheet/tree/main#system-info-and-accounts) | 
| [Software, services and programms](https://github.com/Ahmed-AL-Maghraby/Windows-Registry-Analysis-Cheat-Sheet/tree/main#software-services-and-programms) |
| [Network, Share and Backups](https://github.com/Ahmed-AL-Maghraby/Windows-Registry-Analysis-Cheat-Sheet/tree/main#network-share-and-backups) |
| [Hardware, printers and External/USB device](https://github.com/Ahmed-AL-Maghraby/Windows-Registry-Analysis-Cheat-Sheet/tree/main#hardware-printers-and-externalusb-device) |
| [Files and Folders](https://github.com/Ahmed-AL-Maghraby/Windows-Registry-Analysis-Cheat-Sheet/tree/main#files-and-folders) |

<br>

<br>


### System info and accounts

<br>

| Registry keys | Description |
| -------------------- | -------------------- |
| HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\ComputerName | contains information about the computer name and domain membership |
| HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation | contains information about the time zone settings on the system |
| HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management | contains information about memory management settings on the system |
| HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Environment  | contains environment variables that are set on the system |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList | contains information about the user profiles that are configured on the system |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Windows | contains information about the system's graphical user interface (GUI) settings, including the desktop background and screen saver |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontSubstitutes | contains information about font substitutions on the system |
| SAM\Domains\Account\Users | SAM hive and user information | 
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System | contains information about system policies that are enforced on the system |

<br> <br> 

### Software, services and programms

<br>

| Registry keys | Description |
| -------------------- | -------------------- |
| HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services | contains information about the services that are installed on the system |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run | contains a list of programs that are automatically started when the system boots up |
| USER.DAT\Software\Microsoft\Windows\Currentversion\Explorer\UserAssist\{GUID}\Count | - information about the programs launched <br> - the time of their launch, and the number of times they were executed <br> - programs that were run using the command line can't be found in the User Assist keys <br> -  amount of time a process is in focus |
| SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache | stores file name, file size, and last modified time of the executables |
| + SYSTEM\CurrentControlSet\Services\bam\UserSettings\{SID} <br> + SYSTEM\CurrentControlSet\Services\dam\UserSettings\{SID} | saves the full path of the executed programs |
| C:\Windows\AppCompat\Programs\Amcache.hve | - Amcache Hive : save information on programs that were recently run <br> - This data includes execution path, installation, execution and deletion times, and SHA1 hashes of the executed programs |
| NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Run <br> NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\RunOnce <br> SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce <br> SOFTWARE\Microsoft\Windows\CurrentVersion\policies\Explorer\Run <br> SOFTWARE\Microsoft\Windows\CurrentVersion\Run | Autostart Programs (Autoruns) |
| HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU | Run command history |

<br> <br> 

### Network, Share and Backups

<br>

| Registry keys | Description |
| -------------------- | -------------------- |
| HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters | contains information about the system's TCP/IP settings, such as the IP address and subnet mask |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings | contains information about the system's Internet settings, including the browser history and cookies |
|  HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces | settings for IP Address |
| - SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Unmanaged <br> - SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Managed | Past Networks |
| SYSTEM\CurrentControlSet\Services\LanmanServer\Shares | Windows shares |
| \Software\Microsoft\Windows NT\CurrentVersion\NetworkList | VPN Connection |
| HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Winsock2\Parameters | contains information about the system's Winsock settings, which are used for network communication |
| - C:\Windows\System32\Config\RegBack <br> - directory every ten days. registry keys might have been deleted/modified recently | Backups - RegBack |

<br> <br>



### Hardware, printers and External/USB device

<br>

| Registry keys | Description |
| -------------------- | -------------------- |
| HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum | contains information about hardware devices that are installed on the system |
| _LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR | This key contains information about the external devices that have been connected to the system, including the manufacturer, model, and serial number |
| _LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USB | This key contains information about the USB controllers and hubs on the system, as well as the devices connected to them |
| _LOCAL_MACHINE\SYSTEM\MountedDevices | This key contains information about the mounted volumes on the system, including external USB devices | It can be used to determine the drive letter assigned to a particular device |
| _CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\MountPoints2 | This key contains information about the mounted volumes on the system, including external USB devices | It can be used to determine the drive letter assigned to a particular device |
| _CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU | This key contains information about the most recently accessed files and folders on external USB devices | It can be used to determine what files were accessed and when |
| _CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\USBStor | This key contains information about external USB devices that have been connected to the system, including the device ID, the drive letter, and the last time the device was connected |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Drivers32 | contains information about audio drivers on the system |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Print\Printers | contains information about installed printers on the system |  


<br> <br>



### Files and Folders

<br>

| Registry keys | Description |
| -------------------- | -------------------- |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders | contains information about the locations of various system folders, such as the desktop and the Start menu |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs | contains information about recently opened documents |
| HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer | contains information about Explorer policies that are enforced on the system |
| - NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths <br> - NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\WordWheelQuery | Windows Explorer Address/Search Bars |
| -NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU <br> - NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU | Open/Save and LastVisited Dialog MRUs |
| - NTUSER.DAT\Software\Microsoft\Office\VERSION <br> - NTUSER.DAT\Software\Microsoft\Office\VERSION\UserMRU\LiveID_####\FileMRU | Office Recent Files |


<br> <br> <br> <br> 

