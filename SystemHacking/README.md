# SYSTEM HACKING
1. GAINING ACCESS
2. ESCALATING PRIVILEGES
3. MAINTAINING ACCESS
4. CLEARING LOGS

## GAINING ACCESS
### ITS A SCENARIO. WE WENT SYSTEM HACKING.
LLMNR (Link Local Multicast Name Resolution) and NBT-NS (NetBIOS Name Service) are two main elements of Windows OSes that are used to perform name resolution for hosts present on the same link. These services are enabled by default in Windows OSes and can be used to extract the password hashes from a user. <br> <br>
Responder is an LLMNR, NBT-NS, and MDNS poisoner. It responds to specific NBT-NS (NetBIOS Name Service) queries based on their name suffix. By default, the tool only responds to a File Server Service request, which is for SMB. <br>
![image](https://user-images.githubusercontent.com/56624593/148822267-ea929bfd-bcc5-44f3-b35a-53c954b0441f.png) <br>

Now we crack the captured hash using john
![image](https://user-images.githubusercontent.com/56624593/148822631-ed8fb135-33c9-4b88-9072-e2b0842aa970.png) <br>
# 
### L0phtCrack
It recovers lost Microsoft Windows passwords with the help of a dictionary, hybrid, rainbow table, and brute-force attacks. <br>

