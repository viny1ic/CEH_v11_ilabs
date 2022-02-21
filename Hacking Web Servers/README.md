# WEB SERVER HACKING
## RECON
### Information gathering using Ghost Eye
Ghost Eye gathers information such as Whois lookup, DNS lookup, EtherApe, Nmap port scan, HTTP header grabber, Clickjacking test, Robots.txt scanner, Link grabber, IP location finder, and traceroute.<br>

![image](https://user-images.githubusercontent.com/56624593/155004182-bca5e62b-f242-42dc-873b-dc21dea5dc9a.png)

### Recon using Skipfish
prepares an interactive sitemap for the targeted site by carrying out a recursive crawl and dictionary-based probes. The resulting map is then annotated with the output from a number of active (but hopefully non-disruptive) security checks. <br>
```skipfish -o /root/test -S /usr/share/skipfish/dictionaries/complete.wl http://[victim IP]:8080```<br>
![image](https://user-images.githubusercontent.com/56624593/155004864-2749ee36-51b5-4e0c-bfff-865664a5765a.png)<br>

<b>RESULT:</b><br>
![image](https://user-images.githubusercontent.com/56624593/155004995-91d3e952-02b6-45f3-86ca-50a86351f67c.png)

### Footprinting using httprecon
This tool performs banner-grabbing attacks, status code enumeration, and header ordering analysis on its target web server. <br>
![image](https://user-images.githubusercontent.com/56624593/155005344-3f3eb326-b8b4-4bf2-8059-e2e6b08bc753.png)<br>
attackers can manipulate HTTP vulnerabilities revealed in footprinting and recon in order to perform malicious activities such as sniffing over the HTTP channel etc.

### Footprinting using Netcat and Telnet
Netcat is a networking utility that reads and writes data across network connections, using the TCP/IP protocol.<br>
Telnet is a client-server network protocol. It is widely used on the Internet or LANs. It provides the login session for a user on the Internet.<br>

![image](https://user-images.githubusercontent.com/56624593/155006030-bbc95bd5-77ba-43e3-a612-d9916092e9b3.png)<br>
![image](https://user-images.githubusercontent.com/56624593/155006228-8dd5527d-03c7-46de-8660-f5b95827f4f0.png)<br>

### Enumeration using Nmap Scripting Engine (NSE)
Nmap, along with Nmap Scripting Engine, can extract a lot of valuable information from the target web server. In addition to Nmap commands, Nmap Scripting Engine (NSE)provides scripts that reveal various useful information about the target web server to an attacker.<br>
Basic Enum: ```nmap -sV --script=http-enum [target website]```<br>
![image](https://user-images.githubusercontent.com/56624593/155006558-78b7b33b-83dc-462d-b642-fed1cc2125c6.png)<br>

HTTP Trace: ```nmap --script http-trace -d [target website```<br>
![image](https://user-images.githubusercontent.com/56624593/155007019-00e0c9ca-3159-44b5-a601-e5e1ac746dac.png)<br>

Check for firewall/IDS/IPS: ```nmap -p80 --script http-waf-detect [target website```<br>
![image](https://user-images.githubusercontent.com/56624593/155007337-835fd848-7b11-45bd-97c8-134b2eea534f.png)<br>

# HACKING WEB SERVERS
## EXAMPLE
## Bruteforcing FPT using THC-Hydra
```hydra -L [Username Wordlist] -P [password wordlist] ftp://[Target Machine]```<br>
![image](https://user-images.githubusercontent.com/56624593/155009364-cf7a5f6d-7061-4809-84ca-73f2de62e98a.png)<br>



