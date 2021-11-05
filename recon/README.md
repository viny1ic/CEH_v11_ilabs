# FOOTPRINTING AND RECONNAISSANCE


## 1. FOOTPRINTING THROUGH SEARCH ENGINES
#### SOME COMMON DORKS

    cache: This operator allows you to view cached version of the web page. [cache:www.google.com]- Query returns the cached version of the website www.google.com

    allinurl: This operator restricts results to pages containing all the query terms specified in the URL. [allinurl: google career]—Query returns only pages containing the words “google” and “career” in the URL

    inurl: This operator restricts the results to pages containing the word specified in the URL [inurl: copy site:www.google.com]—Query returns only pages in Google site in which the URL has the word “copy”

    allintitle: This operator restricts results to pages containing all the query terms specified in the title. [allintitle: detect malware]—Query returns only pages containing the words “detect” and “malware” in the title

    inanchor: This operator restricts results to pages containing the query terms specified in the anchor text on links to the page. [Anti-virus inanchor:Norton]—Query returns only pages with anchor text on links to the pages containing the word “Norton” and the page containing the word “Anti-virus”

    allinanchor: This operator restricts results to pages containing all query terms specified in the anchor text on links to the page. [allinanchor: best cloud service provider]—Query returns only pages in which the anchor text on links to the pages contain the words “best,” “cloud,” “service,” and “provider”

    link: This operator searches websites or pages that contain links to the specified website or page. [link:www.googleguide.com]—Finds pages that point to Google Guide’s home page

    related: This operator displays websites that are similar or related to the URL specified. [related:www.certifiedhacker.com]—Query provides the Google search engine results page with websites similar to certifiedhacker.com

    info: This operator finds information for the specified web page. [info:gothotel.com]—Query provides information about the national hotel directory GotHotel.com home page

    location: This operator finds information for a specific location. [location: 4 seasons restaurant]—Query give you results based around the term 4 seasons restaurant

#### FTP SEARCH ENGINE
https://www.searchftps.net/ <br>
You can also use FTP search engines such as Global FTP Search Engine (https://globalfilesearch.com), FreewareWeb FTP File Search (http://www.freewareweb.com), etc. to gather crucial FTP information about the target organization.

#### IOT SEARCH ENGINE
shodan.io <br>
You can also use FTP search engines such as Global FTP Search Engine (https://globalfilesearch.com), FreewareWeb FTP File Search (http://www.freewareweb.com), etc. to gather crucial FTP information about the target organization.
## 2. FOOTPRINTING THROUGH WEB SERVICES
    Find the Company’s Domains and Sub-domains using Netcraft
    
    Gather Personal Information using PeekYou Online People Search Service
    You can also use pipl (https://pipl.com), Intelius (https://www.intelius.com), BeenVerified (https://www.beenverified.com), etc., which are people search services to gather personal information of key employees in the target organization.
    
    Gather an Email List using theHarvester
    
    Gather Information using Deep and Dark Web Searching
    
    Determine Target OS Through Passive Footprinting
    https://censys.io/domain?q=

## 3. FOOTPRINTING  THROUGH SOCIAL NETWORKING SITES
    sherlock

    https://followerwonk.com/analyze



## 4. WEBSITE FOOTPRINTING
    finding IP, frame size and hop number using ping

    https://centralops.net

    using web data extractor

    You can also use other web spiders such as ParseHub  https://www.parsehub.com), SpiderFoot (https://www.piderfoot.net), etc. to extract the target organization’s data.

    Mirror a Target Website using HTTrack Web Site Copier

    You can also use other mirroring tools such as NCollector Studio (http://www.calluna-software.com), Cyotek WebCopy (https://www.cyotek.com), etc. to mirror a target website.

    Gather a Wordlist from the Target Website using CeWL 

## 5. EMAIL FOOTPRINTING

    email header analysis

## 6. WHOIS FOOTPRINTING

## 7. DNS FOOTPRINTING
    using nslookup
        find CNAME record, find server IP using CNAME

    reverse IP lookup

    dnsrecon (to find dns pointers of given ip/ ip range)
## 8. NETWORK FOOTPRINTING
    using ARIN to find the network range

    traceroute

## 9. USING VARIOUS FOOTPRINTING TOOLS
    maltego

    recon-ng

    OSRFramework

    billcipher

    OSINT Framework
