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

### Exploit DB
```www.exploit-db.com``` <br>
you can click any of the latest vulnerabilities to view detailed information, or you can search for a specific vulnerability by entering its name in the Search field. <br>
eg: if we search for <b>Remote</b> exploits for <b>Windows_x86-64</b>, we stumble across a buffer overflow vulnerability. namely, <b>CloudMe Sync 1.11.2 Buffer Overflow - WoW64</b> This exploit code can further be used to exploit vulnerabilities in the target system. <br>

### TheFatRat
TheFatRat is an exploitation tool that compiles malware with a popular payload that can then be executed on Windows, Android, and Mac OSes. The software offers an easy way to create backdoors and payloads that can bypass most anti-viruses. <br>
![image](https://user-images.githubusercontent.com/56624593/149379492-c25d4379-c90a-40c3-b4a4-17bb9e2cbf21.png) <br>
lets create a malicious word doc here (by selecting the [6] option)<br>
![image](https://user-images.githubusercontent.com/56624593/149379832-5b5ee5e3-f5b0-45c8-bbd0-6b06584b95db.png) <br>
after the exe is created, jump back to TheFatRat main menu and select option [7] <br>
select option [2] and generate the malicious document using the exe generated earlier <br>
send it to the victim and use msfconsole to start a listener <br>
![image](https://user-images.githubusercontent.com/56624593/149382103-fd9bae6d-dd0b-4915-a9cc-3228628cf4d8.png) <br>
open the doc and enable editing. and we get a meterpreter session in our attacking machine <br>
![image](https://user-images.githubusercontent.com/56624593/149382806-c970a629-126e-4779-a4a7-39317246b93a.png)

### BUFFER OVERFLOW ATTACKS
This vulnerability allows the application to exceed the buffer while writing data to the buffer and overwrite neighboring memory locations. Further, this vulnerability leads to erratic system behavior, system crash, memory access errors, etc. It can be used to inject malicious code to a pre existing binary. <br>
various tools like vulnserver and Immunity debugger can be used to look for buffer overflow attacks, and then these binaries can be fuzzed to find out a way to exploit the buffer overflow vulnerability.
