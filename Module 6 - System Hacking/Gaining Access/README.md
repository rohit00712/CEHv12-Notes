
# SYSTEM HACKING

* Gaining Access
* Escalating Privileges
* Maintaining Access 
* Clearing Logs

-------------------------------------------------------

## Gaining Access

### Microsoft Authentication

* **Security Accounts Manager (SAM) Database**

Windows stores user passwords in SAM, or in the `Active Directory` database in domains. Passwords are never stored in clear text and are hashed, and the results are stored in the SAM

* **NTLM Authentication**

The NTLM authentication protocol types are as follows: `NTLM authentication protocol` and `LM authentication protocol`

These protocols store the user's password in the `SAM database` using different hashing methods

* **Kerberos Authentication**

Microsoft has upgraded its `default authentication protocol` to Kerberos which provides a stronger authentication for client/server applications than NTLM

### 1.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### 2.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### 3.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

--------------------------------------------------

## Password Cracking

* Password cracking techniques are used to recover passwords from computer systems

* Attackers use password cracking techniques to gain unauthorized access to vulnerable systems

### Types of Password Attacks

### 4.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Non-Electronic Attacks

### 5.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Active Online Attacks

### 6.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Active Online Attacks: Password Spraying Attack and Mask Attack

### 7.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

#### CrackMapExec

`crackmapexec smb <IP> —u users . txt —p passwords . txt`

Run the following command to cross-check whether lockout occurred during the
spraying process:

`spray.sh -smb <targetIP> <usernameList> <AttemptsPerLockoutPeriod> <LockoutPeriodInMinutes> <DOMAIN>`

#### Hashcat

`hashcat -a 3 -m 0 md5_hashes.txt ?l?l?l?d?d?d` 

### Active Online Attacks: Password Guessing

### 8.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Default Password

### 9.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Active Online Attacks: Trojans/Spyware/Keyloggers

### 10.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Active Online Attacks: Hash Injection/Pass-the-Hash (PtH) Attack

### 11.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Active Online Attacks: LLMNR/NBT-NS Poisoning

LLMNR is a protocol used to resolve the names of neighboring computers on a local network.

NBT-NS is a protocol used by Windows to resolve NetBIOS names to IP addresses.

### 12.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Active Online Attacks: Cracking Kerberos Password

### 13.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Active Online Attacks: Pass the Ticket Attack

### 14.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Other Active Online Attacks

### 15.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Passive Online Attacks

### Passive Online Attacks: Wire Sniffing

### 16.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Passive Online Attacks: Man-in-the-Middle/Manipulator-in-the-Middle and Replay Attacks

### 17.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

### Offline Attacks: Rainbow Table Attack

### 18.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Offline Attacks: Distributed Network Attack

### 19.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Password Recovery Tools

### 20.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Tools to Extract the Password Hashes

### 21.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Password Cracking Using Domain Password Audit Tool (DPAT)

### 22.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Password-Cracking Tools: LOphtCrack and ophcrack

### 23.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Password-Cracking Tools

### 24.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Password salting

### 25.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### How to Defend against Password Cracking

### 26.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### 27.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here) 

### How to Defend against LLMNR/NBT-NS Poisoning

### 28.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Tools to Detect LLMNR/NBT-NS Poisoning

### 29.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

* got-responder

-------------------------------------------------------

### Vulnerability Exploitation

### 30.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Exploit Sites

### 31.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

* [Exploit Database](https://exploit-db.com) 

* [VulDB](https://vuldb.com)

* [Vulners](https://vulners.com)

* [MITRE CVE](https://cve.org)

-------------------------------------------------------

## Buffer Overflow

### 32.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Types of Buffer Overflow: Stack-Based Buffer Overflow

### 33.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

### Types of Buffer Overflow: Heap-Based Buffer Overflow

### 34.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Return-Oriented Programming (ROP) Attack

### 35.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Exploit Chaining

### 36.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Active Directory Enumeration Using PowerView

Before performing enumeration using PowerView, attackers disable the security monitoring option using the following command:
`Set—MpPreference —DisableRea1timeMonitoring $true`

### 37.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Domain Mapping and Exploitation with Bloodhound

### 38.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Identifying Insecurities Using GhostPack Seatbelt

GhostPack contains different toolsets of C# implementations of PowerShell functionality. It includes Seatbelt, SharpUp, SharpRoast, SharpDump, SafetyKatz, and SharpWMl. 

### 39.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Buffer Overflow Detection Tools

### 40.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Defending against Buffer Overflows

### 41.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

--------------------------------------------------------------------------------------------------------------
























## Screenshots

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

