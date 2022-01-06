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

## 3. Perform LDAP enumeration

## 4. Perform NFS enumeration

## 5. Perform DNS enumeration

## 6. Perform RPC, SMB, and FTP enumeration

## 7. Perform enumeration using various enumeration tools
