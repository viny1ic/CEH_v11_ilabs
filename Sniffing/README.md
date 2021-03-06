# ACTIVE SNIFFING

## MAC Flooding
MAC flooding is a technique used to compromise the security of network switches that connect network segments or network devices. Attackers use the MAC flooding technique to force a switch to act as a hub, so they can easily sniff the traffic.<br>
use the command ```macof -i <interface> -n <no of packets>```<br>
![image](https://user-images.githubusercontent.com/56624593/151204105-c8fdb4a3-ac07-4472-9999-423afa61f7a6.png)

##DHCP starvation
In a DHCP starvation attack, an attacker floods the DHCP server by sending a large number of DHCP requests and uses all available IP addresses that the DHCP server can issue. As a result, the server cannot issue any more IP addresses, leading to a Denial-of-Service (DoS) attack.<br>

we will use the yersinia tool to perform DHCP starvation.
1. run command ```yersinia -I``` to run yersinia in interactive mode.<br>
![image](https://user-images.githubusercontent.com/56624593/151206310-e31297a3-1bca-4218-83c2-a0b16338eccd.png)
2. press ```F2``` to select DHCP mode.<br>
![image](https://user-images.githubusercontent.com/56624593/151206428-e1b77262-f0d5-4140-98e9-9b3ba6a9cf4f.png)
3. press ```x``` to list available attacks
4. press 1 to start a DHCP starvation attack.<br>
![image](https://user-images.githubusercontent.com/56624593/151206618-b4a6aaaf-3863-4340-9903-1057cb738954.png)
5. press ```q``` to stop the attack.

## ARP poisoning
arpspoof redirects packets from a target host (or all hosts) on the LAN intended for another host on the LAN by forging ARP replies. This is an extremely effective way of sniffing traffic on a switch.<br>
we will be using the tool **arpspoof** to perform the attack
1. Spoof the traffic from the gateway to the victim by running the command ```arpspoof -i <interface> -t <gateway> <victim>```
2. spoof the traffic from the victim to the gateway by running the command ```arpspoof -i <interface> -t <victim> <gateway>```<br>
![image](https://user-images.githubusercontent.com/56624593/151208545-4d375e98-1b32-4d5f-aae4-42d52972c717.png)

## Man In The Middle (MITM) attack
An MITM attack is used to intrude into an existing connection between systems and to intercept the network traffic being transmitted in the network. The attacker can perform actions like capturing, blocking, and modifying the network traffic.<br>
An MITM attack can also be used to steal valuable network data like login credentials, banking details etc.<br>
tools like bettercap, cain & abel etc can be used to perform MITM attacks. <br>
Cain and Abel is a simple windows GUI tool that can be installed and used like so:<br>
1. open Cain & Abel and select the configure option. a configuration dialogue box will appear. 
![image](https://user-images.githubusercontent.com/56624593/151210787-645fd15b-a41a-46df-aebc-07b4aed4b354.png)<br>
2. select the start sniffer option to start sniffing the network
3. in the sniffer tab, click the + option and select the scan mac addresses, and select the subnet you want to scan.<br>
![image](https://user-images.githubusercontent.com/56624593/151211464-b14c3a79-65f4-4718-b119-b08cb6f5a530.png)
4. select the APR tab at the bottom of the window.
5. click the + icon, a New ARP Poison Routing window appears. select the desired IPs to monitor the traffic from.<br>
![image](https://user-images.githubusercontent.com/56624593/151212074-57c66d09-fec3-4857-9eeb-3109a023b487.png)
6. Click the Start APR option to start capturing network packets.

## MAC address spoofing
The attacker first retrieves the MAC addresses of clients who are actively associated with the switch port. Then, the attacker spoofs their own MAC address with the MAC address of the legitimate client.<br>
We can use tools like TMAC and SMAC to perform MAC spoofing. they are simple GUI tools for windows.

## USING SNIFFING TOOLS
Sniffing tools like the SteelCentral packet analyzer and the omnipeek network protocol analyzer can be used to easily sniff the network. these tools have a GUI so they are user friendly. any sensitive information like passwords will be captured while sniffing using any of the tools

## DETECTING SNIFFING IN YOUR NETWORK
any dedvice that is sniffing in a network, runs on promiscuous mode. These sniffers leave no trace and are hard to detect. some of the methods of detecting sniffing are:
### DETECTING SNIFFING IN A SWITCH BASED NETWORK
ARP spoofing succeeds by changing the IP address of the attacker???s computer to the IP address of the target computer.<br>
to detect duplicate IPs and ARP request storms (indicators of ARP spoofing), we will use wireshark.
1. start wireshark, go to edit -> preferences -> protocols -> ARP/RARP.
2. Select the Detect ARP request storms checkbox.
3. select the Detect duplicate IP addresses configuration checkbox.
4. start capturing network data.
5. stop capturing data when sufficient data is collected.
6. go to the analyse tab -> expert information.
7. warnings will be shown for duplicate IPs and ARP storms (if exist)<br>
![image](https://user-images.githubusercontent.com/56624593/151594798-3fd32333-6253-4880-a043-f8b885f6eec5.png)

### DETECTING USING XArp:
XArp is a simple windows GUI tool that monitors the system and alerts the user if they are under a man in the middle attack (ARP spoofing)<br>
![image](https://user-images.githubusercontent.com/56624593/151595434-32b180e3-c34e-4347-b71a-0246181d98c2.png)

### USING NMAP AND NetScanTools TO DETECT PROMISCUOUS MODE
sample nmap command:<br>
```nmap --script=sniffer-detect [Target IP Address/ IP Address Range] ```<br>
![image](https://user-images.githubusercontent.com/56624593/151595737-0e0b914e-34e2-4c10-999b-edf1096e458c.png)<br><br>
NetScanTools is a similar windows GUI tool that can detect promiscuous mode users in the system.<br>
![image](https://user-images.githubusercontent.com/56624593/151595908-ee2f4dac-4f59-4930-a2f4-3119277a0731.png)<br>



