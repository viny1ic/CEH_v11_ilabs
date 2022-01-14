# PRIVILEGE ESCALATION

Privilege escalation is required when you want to access system resources that you are not authorized to access. It takes place in two forms: vertical privilege escalation and horizontal privilege escalation. <br>
* Horizontal Privilege Escalation: An unauthorized user tries to access the resources, functions, and other privileges that belong to an authorized user who has similar access permissions
* Vertical Privilege Escalation: An unauthorized user tries to gain access to the resources and functions of a user with higher privileges such as an application or site administrator <br>
#
There are several methods to perform privilege escalation depending on the scenario. various vulnerabilities and misconfigurations can be used to escalate privileges to achieve the purpose of the exploit. <br>
There are various scripts that can be run on the victim system that automatically look for priv esc opportunities and then exploit them. <br>
#
check the current system privileges to get password hashes using ```run post/windows/smart_hashdump``` <br>
we can use one of the various priv esc exploits present in metasploit like the ```bypassuac_fodhelper``` exploit.
to use it, execute: ```use exploit/windows/local/bypassuac_fodhelper ```, configure the respective details about the session and payload, and exploit.
the script would have created a new meterpreter session for us with elevated privileges. <br>
![image](https://user-images.githubusercontent.com/56624593/149572965-1e6c1e3a-34b2-4482-950b-0f001b9f1491.png) <br>
use the ```getuid``` to get the current user ID. <br>
use the ```getsystem``` command to elevate your privileges.<br>
![image](https://user-images.githubusercontent.com/56624593/149574133-08f7f5ad-8968-44e0-947a-682863e9f99d.png)<br>

now lets see if we can get the system password hashes by runniung ```run post/windows/smart_hashdump```<br>
![image](https://user-images.githubusercontent.com/56624593/149574537-9d33e2a5-ed58-45c1-b8f9-d5ec643ef33b.png)



