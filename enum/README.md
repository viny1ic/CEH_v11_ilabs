# ENUMERATION
## OBJECTIVES
### extract info about target containing (but not limited to): 
* Machine names, their OSes, services, and ports
* Network resources
* Usernames and user groups
* Lists of shares on individual hosts on the network
* Policies and passwords
* Routing tables
* Audit and service settings
* SNMP and FQDN details

## 1. Perform NetBIOS enumeration
### USING WINDOWS CLI TOOLS
    display netbios name table of a machine:
    nbtstat -a [IP address of the remote machine]
![image](https://user-images.githubusercontent.com/56624593/148431279-438eaac5-62ab-4923-b32f-f0e326002d75.png)

    display contents of the NetBIOS name cache of a machine:
    nbtstat -c
![image](https://user-images.githubusercontent.com/56624593/148431514-030b9604-6ee8-42b8-9468-a211b53ba28e.png)

    display information about the target such as connection status, shared folder/drive and network information
    net use
![image](https://user-images.githubusercontent.com/56624593/148431664-81a80dfc-d8b8-4497-891b-2def93c9dda1.png)

### USING NMAP NSE SCRIPT:
    nmap --script nbstat.nse [IP address of the remote machine]
![image](https://user-images.githubusercontent.com/56624593/148432346-c70acc52-08e6-4ba2-8ca3-dc42eeaf0187.png)
    
## 2. Perform SNMP enumeration
### USING SNMP-CHECK:
    ```snmp-check```
![image](https://user-images.githubusercontent.com/56624593/148436256-27dffcc6-0daa-458d-89b2-7dc92cd531be.png)
    information available using this tool:
     Network information, Network interfaces, Network IP and Routing information, TCP connections, listening ports, Processes, Storage information, File system information, 
     Device information, Share, etc.
## 3. Perform LDAP enumeration
### USE ADexplorer
![image](https://user-images.githubusercontent.com/56624593/148437662-7d92ce7b-afc1-4ef2-9754-d5a86875a2fd.png)
the attributes can be viewed and even modified
## 4. Perform NFS enumeration
### USING SuperEnum
## 5. Perform DNS enumeration
BASIC DNS ENUM CAN BE DONE USING THE ```nslookup``` COMMAND
### USING ZONE TRANSFER
```dig ns [domain name]``` <br>
![image](https://user-images.githubusercontent.com/56624593/148812390-22410873-9c1c-404d-b2ec-baf8f78e6850.png) <br>
now we check if zone transfer is possible or not: <br>
```dig @[[NameServer]] [[Target Domain]] axfr```
![image](https://user-images.githubusercontent.com/56624593/148812814-cf28728b-0b39-4684-a757-4bbcfe8f5f61.png) <br>
in this case, zone transfer is not possible
### USING DNS CACHE SNOOPING

### USING DNSSEC ZONE WALKING
DNSSEC zone walking is a DNS enumeration technique that is used to obtain the internal records of the target DNS server if the DNS zone is not properly configured. <br>
```dnsrecon -d [domain name] -z``` <br>
above command tries to perform DNSSEC zone walking <br>
![image](https://user-images.githubusercontent.com/56624593/148813618-61b3a509-a591-45a4-9b77-f158858e449b.png)

## 6. Perform RPC, SMB, and FTP enumeration
```nmap -p [port] -A [target ip]``` <br>
In this command, -p specifies the port to be scanned and -A specifies aggressive scan. The aggressive scan option supports OS detection (-O), version scanning (-sV), script scanning (-sC), and traceroute (--traceroute).

## 7. Perform enumeration using various enumeration tools
1. Global Network Inventory is used as an audit scanner in zero deployment and agent-free environments. It scans single or multiple computers by IP range or domain, as defined by the Global Network Inventory host file.
2. Advanced IP Scanner provides various types of information about the computers on a target network. The program shows all network devices, gives you access to shared folders, provides remote control of computers (via RDP and Radmin), and can even remotely switch computers off.
