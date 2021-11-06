# NETWORK SCANNING

## 1. HOST DISCOVERY
### NMAP
    ARP ping scan
    nmap -sn -PR <target>  (-sn = disable port scan; -PR = perform ARP ping scan)

    UDP scan
    nmap -sn -PU [Target IP Address]   (-PU: performs the UDP ping scan.)

    ICMP ECHO ping scan
    nmap -sn -PE [Target IP Address]   (-PE: performs the ICMP ECHO ping scan.)

    ICMP Timestamp and Address Mask Ping Scan: These techniques are alternatives for the traditional ICMP ECHO ping scan, which are used to determine whether the target host is live specifically when administrators block the ICMP ECHO pings.

    ICMP timestamp ping scan
    nmap -sn -PP [target IP address]

    ICMP address mask ping scan
    nmap -sn -PM [target IP address]

    TCP ACK Ping Scan: This technique sends empty TCP ACK packets to the target host; an RST response means that the host is active.

    nmap -sn -PA [target IP address]

    IP Protocol Ping Scan: This technique sends different probe packets of different IP protocols to the target host, any response from any probe indicates that a host is active.

    nmap -sn -PO [target IP address]

### ANGRY IP SCANNER

You can also use other ping sweep tools such as SolarWinds Engineer’s Toolset (https://www.solarwinds.com), NetScanTools Pro (https://www.netscantools.com), Colasoft Ping Tool (https://www.colasoft.com), Visual Ping Tester (http://www.pingtester.net), and OpUtils (https://www.manageengine.com) to discover active hosts in the target network. <br>

## 2. PORT AND SERVICE SCAN


## 3. OS DISCOVERY

## 4. SCAN BEYOND IDS AND FIREWALL

## 5. NETWORK DIAGRAMS

## 6. USING SCANNING TOOLS