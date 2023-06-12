
# Lab : Module 04 - Enumeration

## 1. Perform NetBIOS Enumeration

### 1.1 Perform NetBIOS Enumeration using Windows `Command-Line Utilities`

`nbtstat -a [IP address of the remote machine]`

**Note:** In this command, `-a` displays the NetBIOS name table of a remote computer.

`nbtstat -c`

**Note:** In this command, -c lists the contents of the NetBIOS name cache of the remote
computer.

`net use`

The output displays information about the target
such as connection status, shared folder/drive and network information, as shown in
the screenshot.

### 1.2 Perform NetBIOS Enumeration using `NetBIOS Enumerator`

### 1.3 Perform NetBIOS Enumeration using an `NSE Script`

`nmap -sV -v --script nbstat.nse [Target IP Address]`

**Note:** `-sV` detects the service versions, `-v` enables the verbose output (that is, includes
all hosts and ports in the output), and `--script nbstat.nse` performs the NetBIOS
enumeration.

`nmap -sU -p 137 --script nbstat.nse [Target IP Address]`

**Note:** `-sU` performs a UDP scan, `-p` specifies the port to be scanned, and `--script nbstat.nse` performs the NetBIOS enumeration.

-----------------------------------------------------------------------

## 2 Perform SNMP Enumeration

### 2.1 Perform SNMP Enumeration using `snmp-check`

First, we check port is open or not.

`nmap -sU -p 161 [Target IP Address]`

`snmap-check [Target IP Address]`

It reveals that the extracted SNMP port 161 is being used by the default "public" community string.

### 2.2 Perform SNMP Enumeration using `SoftPerfect Network Scanner`

### 2.3 Perform SNMP Enumeration using `SnmpWalk`

`snmpwalk -v1 -c public [target IP]`

**Note:** `—v:` specifies the SNMP version number (I or 2c or 3) and `—c:` sets a community string.

### 2.4 Perform SNMP Enumeration using `Nmap`

`nmap -sU -p 161 --script=snmp-sysdescr [Target IP Address]`

The result appears displaying information regarding SNMP server type and operating system details.

`nmap -sU -p 161 --script=snmp-processes [Target IP Address]`

The result appears displaying a list of all the running SNMP processes along with the associated ports on the target machine.

`nmap -sU -p 161 --script=snmp-win32-software [Target IP Address]`

The result appears displaying a list of all the applications running on the target machine.

`nmap -sU -p 161 --script=snmap-interfaces [Target IP Address]`

The result appears displaying information about the Operating system, network interfaces, and applications that are installed on the target machine.

-----------------------------------------------------------------------

## 3 Perform LDAP Enumeration

### 3.1 Perform LDAP Enumeration using `Active Directory Explorer` (AD Explorer)

### 3.2 Perform LDAP Enumeration using `Python and Nmap`

### Nmap :

To check the open port.

`nmap -sU -p 389 [Target IP Address]`

`nmap -p 389 --script ldap-brute --script-args ldap.base="cn=users,dc=CEH,dc=com" [Target IP Address]`

**Note:** `-p:` specifies the port to be scanned, `Idap-brute:` to perform brute-force LDAP authentication. `Idap.base:` if set, the script will use it as a base for the password guessing attempts.

### Python :

`python3`

`>>> import ldap3`

`>>> server=ldap3.server('[Target IP Address]',get_info=ldap3.ALL,port=[Target Port])`

`>>> connection=ldap3.Connection(server)`

`>>> connection.bind()`

`>>> server.info`

It will gather information such as `naming context` or `domain name`.

`>>> connection.search(search_base='DC=CEH,DC=com',search_filter='(&(objectclass=*))',search_scope='SUBTREE',attributes='*')`

`True` response indicates that the query is successfully executed.

`>>> connection.entries`

To retrieve all the directory objects.

`>>> connection.search(search_base='DC=CEH,DC=com',search_filter='(&(objectclass=person))',search_scope='SUBTREE',attributes='userpassword')`

`True` response indicates that the query is successfully executed.

`>>> connection.entries`

To dump the entire LDAP information.

### 3.3 Perform LDAP Enumeration using `ldapsearch`

`ldapsearch -h [Target IP Address] -x -s base namingcontexts`

**Note:** `-x:` specifies simple authentication, `-h:` specifies the host, and `-s:` specifies the scope.

`ldapsearch -h [Target IP Address] -x -b "DC=CEH,DC=com"`

`-b :` specifies the base DN for search.

`ldapsearch -h [Target IP Address] -x -b "DC=CEH,DC=com" "objectclass=*"`

To retrieve information related to all the objects in the directory tree.

-----------------------------------------------------------------------

## 4 Perform NFS Enumeration

### 4.1 Perform NFS Enumeration using `RPCScan` and `SuperEnum`

To check the open port

`nmap -p 2049 [Target IP Address]`

### SuperEnum :

`cd SuperEnum`

`echo "[Target IP Address]" >> Target.txt`       //First save target IP.

`./superenum`       //Then enter the target file name.

After the scan is finished, scroll down to review the results.Observe that the port 2049 is open and the NFS service is running on it.

### RPCScan

`cd RPCScan`

`python3 rpc-scan.py [Target IP Address] --rpc`

The result appears, displaying that port 2049 is open, and the NFS service is running on it.

----------------------------------------------------------------------

## 5 Perform DNS Enumeration

## Differnet between DNS Zone Transfer and DNSSEC Zone Walking ?

In summary, DNS zone transfer is a mechanism to replicate DNS zone data between servers for redundancy, while DNSSEC zone walking is an unintended consequence of the original DNSSEC specification that allows enumeration of all records in a DNSSEC-signed zone. However, NSEC5 has been developed to address the privacy and security concerns associated with DNSSEC zone walking.

### 5.1 Perform DNS Enumeration using `Zone Transfer`

### dig : For Linux

`dig ns [Target Domain]`

**Note:** On Linux-based systems, the dig command is used to query the DNS name servers to retrieve information about target `host addresses`, `name servers`, `mail exchanges`, etc.

`dig @[[NameServer]] [[Target Domain]] axfr`

**Note:** In this command, axfr retrieves zone information.

After retrieving DNS `name server` information, the attacker can use one of the servers to test whether the target DNS allows zone transfers or not. In this case, zone transfers are not allowed for the target domain; this is Why the command resulted in the message: Transfer failed. A penetration tester should attempt DNS zone transfers on different `domains` Of the target organization.

### nslookup : For Windows

`nslookup`

`> set querytype=soa`
`> certifiedhacker.com`

The result appears, displaying information about the target domain such as the `primary name server` and `responsible mail addr`.

`> ls -d [Name Server]`

**Note:** In this command, `Is -d` requests a zone transfer of the specified name server.

## 5.2 Perform DNS Enumeration using `DNSSEC Zone Walking`

Tool : DNSRecon

`cd dnsrecon`

`./dnsrecon.py -h`

`./dnsrecon.py -d [Target domain] -z`

**Note: -z specifies that the DNSSEC zone walk be performed with standard enumeration.

Using the DNSRecon tool, the attacker can enumerate general DNS records for a given domain (MX, SOA, NS, A, AAAA, SPF, and TXT). These DNS records contain digital signatures based on public-key cryptography to strengthen authentication in DNS.

## 5.3 Perform DNS Enumeration using `Nmap`

`nmap --script=broadcast-dns-service-discovery [Target Domain]`

The result appears displaying a list Of all the available DNS services on the target host along with their associated ports.

`nmap -T4 -p 53 --script dns-brute [Target Domain]`

The result appears displaying a list of all the subdomains associated with the target host along with their IP addresses.

`nmap --script dns-srv-enum --script-args "dns-srv-enum.domain='[Target Domain]'"`

The result appears displaying various common service (SRV) records for a given domain name.

-----------------------------------------------------------------------

## 6. Perform SMTP Enumeration

### 6.1 Perform SMTP Enumeration using `Nmap`

`nmap -p 25 --script=smtp-enum-users [Target IP Address]`

The result appears displaying a list of all the possible mail users on the target machine.

`nmap -p 25 --script=smtp-open-relay [Target IP Address]`

The result appears displaying a list of open SMTP relays on the target machine.

`nmap -p 25 --script=smtp-command [Target IP Address]`

A list of all the SMTP commands available in the Nmap directory appears. You can further explore the commands to obtain more information on the target host.

**Using this information, the attackers can perform password spraying attacks to gain unauthorized access to the user accounts.**

-----------------------------------------------------------------------

## 7. Perform RPC, SMB, and FTP Enumeration

### 7.1 Perform SMB and RPC Enumeration using `NetScanTools Pro`

### 7.2 Perform RPC, SMB, and FTP Enumeration using `Nmap`

`nmap -p 21 -A [Target IP Address]`        //For FTP enum.

`nmap -T4 -A [Target IP Address]`      

`-A:` specifies aggressive scan. The aggressive scan option supports OS detection (-0), version scanning (-sV), script scanning (-sC), and traceroute (--traceroute).

`nmap -p 445 -A [Target IP Address]`       //For SMB enum.

-----------------------------------------------------------------------

## 8. Perform Enumeration using Various Enumeration Tools

### 8.1 Enumerate Information using `Global Network Inventory`

Global Network Inventory is a powerful and flexible software and hardware inventory system that can be used as an audit scanner in an agent-free and zero deployment environments. It can audit remote computers and even network appliances, including switches, network printers and document centers. It is a network tool that helps system administrators to audit and deploy PC environments. The program also acts as a hardware administration tool since it’s capable of auditing/detecting switches, network printers and other devices on a network. 

### 8.2 Enumerate Network Resources using `Advanced IP Scanner`

Advanced IP Scanner provides various types Of information about the computers on a target network. The program shows all network devices, gives you access to shared folders, provides remote control of computers (via RDP and Radmin), and can even remotely switch computers off.

### 8.3 Enumerate Information from Windows and Samba Hosts using `Enum4linux`

Enum41inux is a tool for enumerating information from Windows and Samba systems. It is used for share enumeration, password policy retrieval, identification of remote OSes, detecting if hosts are in a workgroup or a domain, user listing on hosts, listing group membership information, etc.

`enum4linux -h`

We will first enumerate the NetBIOS information of the target machine.

`enum4linux -u martin -p apple -n [Target IP Address]`

`enum4linux -u martin -p apple -U [Target IP Address]`

-U : retrieves the userlist.

Enum41inux starts enumerating and displays data such as Target Information, Workgroup/Domain, domain SID (security identifier), and the list of users, along with their respective RIDS (relative identifier).

`enum4linux -u martin -p apple -o [Target IP Address]`

-o : retrieves the OS information

`enum4linux -u martin -p apple -P [Target IP Address]`

-P : retrieves the password policy information.

`enum4linux -u martin -p apple -G [Target IP Address]`

-G : retrieves group and member list.

`enum4linux -u martin -p apple -S [Target IP Address]`

-S : retrieves sharelist.

-----------------------------------------------------------------------


































