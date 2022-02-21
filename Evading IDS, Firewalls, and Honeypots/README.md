# EVADING IDS, FIREWALLS AND HONEYPOTS
## OBJECTIVES
* Detect intrusion attempts
* Detect malicious network traffic
* Evade firewalls

## SNORT
Snort is an open-source network intrusion detection system, capable of performing real-time traffic analysis and packet logging on IP networks.<br>
Network monitoring and alert rules can be specified in a text file and the tool will act according to the rules.<br>
* After installation, run ```snort``` in cmd to initialise snort. press CTRL+C after completion.<br>
![image](https://user-images.githubusercontent.com/56624593/152215370-f50e0a5f-9dfb-436f-a237-9b6d500e9758.png)<br>
* run the command ```snort -W``` to list the network details of your system.<br>
![image](https://user-images.githubusercontent.com/56624593/152215522-2c0466f3-68ec-4b23-b1e8-64fe2c96abea.png)<br>
* enable the network interface by using the index number of the interface in the command: ```snort -dev -i <index no>```<br>
![image](https://user-images.githubusercontent.com/56624593/152215841-dbd3f3c3-b0a5-438a-acbc-d0e6c0e63a8d.png)<br>
* Snort will start capturing the traffic passing through the interface now<br>
![image](https://user-images.githubusercontent.com/56624593/152216029-7f187f68-29b8-40e5-98ca-9dbfdb67f262.png)<br>
* Snort configurations can be changed in the snort.conf file<br>
![image](https://user-images.githubusercontent.com/56624593/152216381-3830b7dd-5c56-4fa8-a92a-994ec8914c51.png)<br>
* The rules that govern snort behaviour can be written in a text file and the path to that text file has to be saved in the snort.conf file.<br>
snort.conf:<br>
![image](https://user-images.githubusercontent.com/56624593/152216821-bcf68fbc-a7e5-4a9f-9ea6-ebc9dc45aee1.png)<br>
* In a similar way, other configurations of the conf file can be managed according to the necessity.
* now start the IDS by running ```snort -i<index no> -A console -c <conf file path> -l <log file path> -K ascii```<br>
![image](https://user-images.githubusercontent.com/56624593/152217472-6cc83359-ded4-4070-8cbc-c6a568df0afa.png)<br>


## FIREWALL
various Firewalls like ZoneAlarm can be used to secure our networks. It manages and monitors all incoming and outgoing traffic and shields the network from hackers, malware, and other online threats that put network privacy at risk, and monitors programs for suspicious behavior spotting and stopping new attacks that bypass traditional anti-virus protection.<br>
![image](https://user-images.githubusercontent.com/56624593/152219205-5d92c0e9-be96-4dc3-9f17-df05edbc01e6.png)<br>
URLs can be blocked by clicking the view zones zone -> add zone option<br>
![image](https://user-images.githubusercontent.com/56624593/152219359-56f952e3-fb6c-4efa-a488-98c5748204ac.png)<br>

## HONEYPOT
A honeypot creates a safe environment to capture and interact with unsolicited traffic on a network. HoneyBOT is an easy-to-use solution that is ideal for network security research or as part of an early-warning IDS.<br>
![image](https://user-images.githubusercontent.com/56624593/152220243-82dc946a-af28-4a94-b5a0-23b109cb01d1.png)<br>
config window:<br>
![image](https://user-images.githubusercontent.com/56624593/152221170-067c1680-a0e5-4235-a874-4ecd13bd2289.png)<br>
After the configuration, the honeypot wil start working<br>
![image](https://user-images.githubusercontent.com/56624593/152221410-ceead2fc-366a-42fa-a7f7-e3ad992148b8.png)<br>

## EVADING FIREWALLS
    Port Scanning
    Firewalking
    Banner Grabbing
    IP Address Spoofing
    Source Routing
    Tiny Fragments
    Using an IP Address in Place of URL
    Using Anonymous Website Surfing Sites
    Using a Proxy Server
    ICMP Tunneling
    ACK Tunneling
    HTTP Tunneling
    SSH Tunneling
    DNS Tunneling
    Through External Systems
    Through MITM Attack
    Through Content
    Through XSS Attack

### Bypassing Firewalls using nmap evasion techniques
* TCP SYN port scan: ```nmap -sS <IP/range>```
* INTENSE SCAN (OS detectoin, version detection, script scanning, traceroute): ```nmap -T<intensity(1-5)> -A```
* Ping Sweep Scan (pings all devices in the network to discover them): ```nmap -sP <IP range>```
* Zombie scan(use an intermediate 'zombie' for the scan): ```nmap -sI <zombie IP> <Victim IP>```

### HTTP/FTP tunneling
This technology encapsulates data inside HTTP traffic (port 80). Many firewalls do not examine the payload of an HTTP packet to confirm that it is legitimate, thus it is possible to tunnel traffic via TCP port 80.
Tools like <b>HTTPHost</b> can be used to carry out HTTP tunneling allows users to bypass the HTTP proxy, which blocks Internet access to e-mail, instant messengers, P2P file sharing, ICQ, News, FTP, IRC, etc.
