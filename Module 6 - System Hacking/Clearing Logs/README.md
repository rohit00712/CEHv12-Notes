
# Demonstrate Techniques to Hide the Evidence of Compromise

The attacker uses the following techniques to cover his/her tracks on the target system

* Disable Auditing
* Clearing Logs
* Manipulating Logs
* Covering Tracks on the Network/OS
* Deleting Files / Hiding Artifacts
* Disabling Windows Functionality

-------------------------------------------------------

## Disable Auditing

`Auditpol.exe` is the command-line utility tool to change audit security settings at the category
and sub-category levels.

Enabling system auditing:

`C:\>auditpol /set /category:"system","account logon" /success:enable /failure:enable`

Disable system auditing:

`C:\>auditpol /set /category:"system","account logon" /success:disable /failure:disable`

-----------------------------------------------------------------------

## Clearing Logs

Download the `Clear_Event_Viewer_Logs.bat` utility

https://www.majorgeeks.com/files/details/clear_all_event_logs_in_event_viewer_in_windows.html

* clear logs using meterpreter

`clearev`

## Clear PowerShell logs using `Clear-EventLog` command

* To clear the entries from the PowerShell event from a local or remote system:

`Clear—EventLog "Windows PowerShell"`

* To clear specific multiple log types from the local and remote systems:

`Clear-EventLog -LogName ODiag, OSession -ComputerName localhost, Server02`

(This command clears all the log entries in Microsoft Office Diagnostics (ODiag) and
Microsoft Office Sessions (OSession) on the local computer and Server02 remote
computer.)

* To clear all logs on the specified systems and then display the event log list:

`Clear-EventLog -LogName application, system -confirm`

## clear event logs using `wevtutil` utility

`wevtutil el` : Display a list of event logs

`wevtutil cl <log_name>` : log_name name of the log to clear, ex: system, application, security.

## Manually Clearing Event Logs

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/1.PNG)

-------------------------------------------------------

## Ways to Clear Online Tracks

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/2.PNG)

-------------------------------------------------------

## Covering BASH Shell Tracks

`more ~/.bash_history` : To view the save command history

* Disabling history

`export HISTSIZE=0`

* Clearing the history

`history -c` : clears the stored history

`history -w` : clears history of current shell

* Clearing the user's complete history

`cat /dev/null > ~.bash_history && history -c && exit`

* Shredding the history

`shred ~/.bash_history` : Shreds the history file, making its content unreadable

`shred ~/.bash_history && cat /dev/null > .bash_history && history -c && exit` : Shreds the history file and clears the evidence of the command

-------------------------------------------------------

## Covering Tracks on a Network

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/3.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/4.PNG)

-------------------------------------------------------

## Covering Tracks on an OS

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/5.PNG)

### Windows

* Modifying Time :

`timestomp file_name.doc -z "<Date> <time>"`

-z "<Date> <time>" : This option allows you to set all three timestamp attributes (Created, Modified, and Accessed) to a specific date and time.

or

`powershell -Command "(Get-Item $File_name).LastWriteTime = $(Get-Date).AddHours(-10)"` : substract 10 hours from current date and time

`powershell -Command "(Get-Item $File_name).LastWriteTime = Get-Date('2022-10-31 12:00:00')"`

### Unix/Linux

* Modifying Date and Time :

`touch -a -d '<date> <time>' $File_name` : last access date and time

`touch -m -d '<date> <time>' $File_name` : last modification date and time

-------------------------------------------------------

## Delete Files using Cipher.exe

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/6.PNG)

When an attacker creates and encrypts a malicious text file, at the time of the encryption
process, a backup file is created. Therefore, if the encryption process is interrupted, the backup
file can be used to recover the data. After the completion of the encryption process, the backup
file is deleted, but this deleted file can be recovered using data recovery software and can then
be used by security personnel for investigation.

To avoid data recovery and cover their tracks, attackers use the Cipher.exe tool to overwrite
the deleted files, first with all zeroes (O x 00), second with all 255s (O x FF), and then finally with
random numbers.

-------------------------------------------------------

## Disable Windows Functionality

* Disable the Last Access Timestamp :

`fsutil` is a utility in Windows used to set the NTFS
volume behavior parameter, DisableLastAccess, which controls enabling or disabling of the last
access timestamp.

`fsutil behavior set disablelastaccess 1` : disable

`fsutil behavior set disablelastaccess 0` : enable

* Disable Windows Hibernation :

Windows Hibernation is a power-saving state in which the contents of a computer's RAM (random access memory) are saved to the hard disk or other non-volatile storage device. When a computer is hibernated, it essentially shuts down, but saves the current state of the operating system, including all open files and programs, to the hard disk.

The hibernate file (Hiberfil.sys) is a hidden system file located in the root directory where the OS is installed. This file contains information regarding the system RAM stored on a hard disk at specific times (when the user selects to hibernate his/her
system). 

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/7.PNG)

or

`powercfg.exe /hibernate off`

* Disable Windows Virtual Memory (Paging File)

Virtual memory, also called a paging file, is a special file in Windows that is used as a compensation when RAM (physical memory) falls short of usable space. For example, if an attacker has an encrypted file and wants to read it, he/she must first decrypt it. This decrypted file stays in the paging file, even after the attacker logs out of the system. Moreover, some third-party programs can be used to store plaintext passwords and other sensitive information temporarily. Therefore, disabling paging in Windows is a crucial step toward covering tracks.

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/14.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/15.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/16.PNG)

* Disable System Restore Points

System restore points contain information about hidden data and previously deleted files. This poses a risk for attackers as the deleted files can be recovered from previous restore points.

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/17.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/18.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/19.PNG)

* Disable Windows Thumbnail Cache

If an attacker has used an image file to hide a malicious file and later
deleted it, a thumbnail of this image is stored inside the thumbs.db file, which reveals
that the deleted file was previously used on the system.

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/20.PNG)

* Disable Windows Prefetch Feature

Prefetch is a Windows feature that stores specific data about the applications that are typically used by the system users. The stored data help in enhancing system performance by reducing the time required to load or start applications.

For example, if an attacker has installed a malicious application and then uninstalled it, a copy of that application will be stored in the Prefetch file. These Prefetch files can be used by security personnel to recover deleted files during the investigation of a security incident.

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/21.PNG)

-------------------------------------------------------

## Hiding Artifacts in Windows, Linux, and macOS

### Hiding Artifacts in Windows

* Hiding Files and Folders

Attackers use the following command with administrator privileges to hide any file or folder in a Windows system:

`attrib +h +s +r <FolderName>`

* Hiding Users

Attackers can create a hidden user account on the victim system using the following command:

`net user <UserName> / add`

Run the following command to activate the account for exploitation:

`net user <UserName> /active : yes`

Run the following command to hide the account when it is not required:

`net user <UserName> / active : no`

* Hiding User Accounts

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/9.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/10.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/11.PNG)

-------------------------------------------------------

## Hiding Artifacts in Linux

* Hiding Files and Folders

`mv MaliciousFile.txt .MaliciousFile.txt`

`mkdir .HiddenMaliciousFiles`

-------------------------------------------------------

## Hiding Artifacts in macOS

* Hiding Files and Folders

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/12.PNG)

-------------------------------------------------------

## Track-Covering Tools

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/8.PNG)


-------------------------------------------------------

## Defending against Covering Tracks

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Clearing%20Logs/images/13.PNG)

-------------------------------------------------------



