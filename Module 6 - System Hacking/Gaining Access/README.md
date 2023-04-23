
# SYSTEM HACKING

* Gaining Access
* Escalating Privileges
* Maintaining Access 
* Clearing Logs

-------------------------------------------------------

## Gaining Access

## Microsoft Authentication

* **Security Accounts Manager (SAM) Database**

Windows stores user passwords in SAM, or in the `Active Directory` database in domains. Passwords are never stored in clear text and are hashed, and the results are stored in the SAM

* **NTLM Authentication**

The NTLM authentication protocol types are as follows: `NTLM authentication protocol` and `LM authentication protocol`

These protocols store the user's password in the `SAM database` using different hashing methods

* **Kerberos Authentication**

Microsoft has upgraded its `default authentication protocol` to Kerberos which provides a stronger authentication for client/server applications than NTLM

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/1.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/2.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/3.PNG)
--------------------------------------------------

## Password Cracking

* Password cracking techniques are used to recover passwords from computer systems

* Attackers use password cracking techniques to gain unauthorized access to vulnerable systems

## Types of Password Attacks

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/4.PNG)

## Non-Electronic Attacks

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/5.PNG)

## Active Online Attacks

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/6.PNG)

## Active Online Attacks: Password Spraying Attack and Mask Attack

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/7.PNG)

### CrackMapExec

`crackmapexec smb <IP> —u users . txt —p passwords . txt`

Run the following command to cross-check whether lockout occurred during the
spraying process:

`spray.sh -smb <targetIP> <usernameList> <AttemptsPerLockoutPeriod> <LockoutPeriodInMinutes> <DOMAIN>`

### Hashcat

`hashcat -a 3 -m 0 md5_hashes.txt ?l?l?l?d?d?d` 

## Active Online Attacks: Password Guessing

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/8.PNG)

## Default Password

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/9.PNG)

### Active Online Attacks: Trojans/Spyware/Keyloggers

### 10.png

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/10.PNG)

## Active Online Attacks: Hash Injection/Pass-the-Hash (PtH) Attack

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/11.PNG)

## Active Online Attacks: LLMNR/NBT-NS Poisoning

LLMNR is a protocol used to resolve the names of neighboring computers on a local network.

NBT-NS is a protocol used by Windows to resolve NetBIOS names to IP addresses.

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/12.PNG)

## Active Online Attacks: Cracking Kerberos Password

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/13.PNG)

## Active Online Attacks: Pass the Ticket Attack

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/14.PNG)

## Other Active Online Attacks

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/15.PNG)

-------------------------------------------------------

## Passive Online Attacks

## Passive Online Attacks: Wire Sniffing

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/16.PNG)

## Passive Online Attacks: Man-in-the-Middle/Manipulator-in-the-Middle and Replay Attacks

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/17.PNG)

-------------------------------------------------------

## Offline Attacks: Rainbow Table Attack

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/18.PNG)

## Offline Attacks: Distributed Network Attack

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/19.PNG)

## Password Recovery Tools

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/20.PNG)

## Tools to Extract the Password Hashes

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/21.PNG)

## Password Cracking Using Domain Password Audit Tool (DPAT)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/22.PNG)

## Password-Cracking Tools: LOphtCrack and ophcrack

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/23.PNG)

## Password-Cracking Tools

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/24.PNG)

## Password salting

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/25.PNG)

## How to Defend against Password Cracking

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/26.PNG)

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/27.PNG) 

## How to Defend against LLMNR/NBT-NS Poisoning

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/28.PNG)

## Tools to Detect LLMNR/NBT-NS Poisoning

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/29.PNG)

* got-responder

-------------------------------------------------------

## Vulnerability Exploitation

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/30.PNG)

## Exploit Sites

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/31.PNG)

* [Exploit Database](https://exploit-db.com) 

* [VulDB](https://vuldb.com)

* [Vulners](https://vulners.com)

* [MITRE CVE](https://cve.org)

-------------------------------------------------------

## Buffer Overflow

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/32.PNG)

## Types of Buffer Overflow: Stack-Based Buffer Overflow

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/33.PNG)

## Types of Buffer Overflow: Heap-Based Buffer Overflow

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/34.PNG)

-------------------------------------------------------

## Return-Oriented Programming (ROP) Attack

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/35.PNG)

## Exploit Chaining

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/36.PNG)

## Active Directory Enumeration Using PowerView

Before performing enumeration using PowerView, attackers disable the security monitoring option using the following command:
`Set—MpPreference —DisableRea1timeMonitoring $true`

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/37.PNG)

## Domain Mapping and Exploitation with Bloodhound

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/38.PNG)

## Identifying Insecurities Using GhostPack Seatbelt

GhostPack contains different toolsets of C# implementations of PowerShell functionality. It includes Seatbelt, SharpUp, SharpRoast, SharpDump, SafetyKatz, and SharpWMl. 

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/39.PNG)

## Buffer Overflow Detection Tools

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/40.PNG)

## Defending against Buffer Overflows

![App Screenshot](https://github.com/rohit00712/CEHv12-Notes/blob/main/Module%206%20-%20System%20Hacking/Gaining%20Access/images/41.PNG)

--------------------------------------------------------------------------------------------------------------
























## Screenshots

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

