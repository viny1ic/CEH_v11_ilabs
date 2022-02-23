# WEB APPLICATION ATTACKS

## BRUTEFORCE USING BURP SUITE
Burp Suite contains key components such as an intercepting proxy, application-aware spider, advanced web application scanner, intruder tool, repeater tool, and sequencer tool. It supports the entire testing process from the initial mapping and analysis of an application’s attack surface to finding and exploiting security vulnerabilities.<br>
1. In order to intercecpt and manipulate the http requests and responses, we must set up a proxy. we can do so by going to the browser and setting up a proxy with IP address 127.0.0.1 and port as 8080 (default). enable this proxy for all protocols.<br>
After this all the packets sent and recieved by the browser will be intercepted by burp proxy.<br>
alternately, burp's own browser client can also be used to eliminate this step.
2. After setting up the proxy, start burpsuite and go to the proxy tab, intercept tab under the proxy tab and make sure the intercept option is enabled.
![image](https://user-images.githubusercontent.com/56624593/155384387-fb458cf4-968d-4e82-b543-bba53bc39854.png)<br>
3. next, go enter the url of the webpage that needs to be bruteforced, while forwarding all the packets that show up in the intercept tab of burpsuite.
4. next, fill in the login fields in the webpage with sample data and click on send.
5. in the intercept tab, look for the request that contains the sample data, forwarding all the packets before it.
6. right click anywhere on this request and select the send to intruder option.<br>
![image](https://user-images.githubusercontent.com/56624593/155384976-19a166aa-98ee-4442-aab8-3b63b7c042a5.png)
7. go to the intruder tab in burpsuite, go to the target sub tab and enter the domain/IP and port of the target. next, go to the positions sub tab, select the attack type (cluster bomb in this case) and select all the parameters of the request that need to be bruteforced, eg: username, password etc.<br>
![image](https://user-images.githubusercontent.com/56624593/155386623-32082d61-93a7-4736-8a0f-99591e669ec3.png)<br>
8. Go to the payload sub tab, load or enter all the payload sets, and hit start attack.<br>
![image](https://user-images.githubusercontent.com/56624593/155386866-0aaf20fa-9835-4f18-ac79-e2657d619d24.png)<br>
![image](https://user-images.githubusercontent.com/56624593/155386919-74a0cdd9-574e-4198-84a7-89b6a0f10c38.png)<br>
keep an eye on the content lengths, time and statuses of the responses. check the responses with a different parameter, it is likely for that response to be a positive one and we have cracked the password. 

## PARAMETER TAMPERING AND XSS
Parameter tampering is a simple form of attack aimed directly at an application’s business logic. A parameter tampering attack exploits vulnerabilities in integrity and logic validation mechanisms that may result in various vulnerabilities.<br>
XSS attacks exploit vulnerabilities in dynamically generated web pages, which enables malicious attackers to inject client-side script into web pages viewed by other users.<br>
for example, if some text field such as the comments section of any content is vulnerable to XSS, we can simply enter some javascript code which will be executed when any other user accesses that comments section.<br>
![image](https://user-images.githubusercontent.com/56624593/155389401-fae837bc-54a9-4b0f-8510-8f99bf633307.png)<br>
![image](https://user-images.githubusercontent.com/56624593/155389424-d7856a21-e7ab-45dc-b125-f4c11a295808.png)<br>




