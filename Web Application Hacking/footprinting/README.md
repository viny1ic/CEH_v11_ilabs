# WEB APPLICATION FOOTPRINTING

## RECON
### Whois
Perform a Whois lookup to gather information about the IP address of the web server and the complete information about the domain such as its registration details, name servers, IP address, and location.<br>
Whois lookup can be performed using various websites that provide the service and also using various comand line tools.<br>

### DNS Interrogation
Perform DNS Interrogation to gather information about the DNS servers, DNS records, and types of servers used by the target organization.<br>
tools like nslookup, DNSRecon etc and various online tools can be used to perform DNS recon of the target.<br>

### Port Scanning
Port scanning is performed to gather information about the open and closed port in a system that hosts the website. It is also used to find out which services are running on the ports that are open.<br>
various Nmap port scanning techniques can be used to perform port scanning, which is covered in detail in the respective part of the repo.

### Banner Grabbing
banner grabbing is used to identify the make, model, and version of the target web server software.<br>
```telnet [target domain/IP] port``` command can be used to perform banner grabbing.<br>
![image](https://user-images.githubusercontent.com/56624593/155377134-179cfab2-f1f2-4080-be53-6e0fbdd08f83.png)<br>

## AUTOMATED TOOLS FOR RECON
### WhatWeb
WhatWeb identifies websites and recognizes web technologies, including content management systems (CMS), blogging platforms, statistics and analytics packages, JavaScript libraries, web servers, and embedded devices. It also identifies version numbers, email addresses, account IDs, web framework modules, SQL errors, and more.<br>
![image](https://user-images.githubusercontent.com/56624593/155377634-56348609-be7c-4575-aa8b-62dde2f81497.png)<br>

### OWASP ZAP
OWASP Zed Attack Proxy (ZAP) is an integrated penetration testing tool for finding vulnerabilities in web applications. It offers automated scanners as well as a set of tools that allow you to find security vulnerabilities manually.<br>
During an automated scan, ZAP first crawls the whole scope using a spider, scanning the pages one after the other for vulnerabilities.
![image](https://user-images.githubusercontent.com/56624593/155378283-90657207-9d89-4ef4-a1ef-cd89e6d3947a.png)<br>
![image](https://user-images.githubusercontent.com/56624593/155378451-156f926c-9c1f-4b9e-9e1a-3cdc759c9fcb.png)

