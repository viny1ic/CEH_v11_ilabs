# COVERING TRACKS
* disable auditing
* clearing logs
* manipulating logs
* covering tracks on network
* covering tracks on OS
* deleting files
* disabling windows functinality

## Manipulate audit policies using AuditPol
Auditpol.exe is the command-line utility tool to change the Audit Security settings at the category and sub-category levels. <br>
* spawn a command prompt with administrator privileges
* run: ```auditpol /get /category:*```<br>
![image](https://user-images.githubusercontent.com/56624593/149820653-f7b71bd3-b550-473b-8561-733d854141c4.png)
* example of editing a policy: ```auditpol /set /category:"system","account logon" /success:enable /failure:enable```
* clear auditing policies using: ```auditpol /clear /y```<br>
![image](https://user-images.githubusercontent.com/56624593/149821274-7b465945-ee4c-4621-b7d7-1833f114acad.png)

## CLEARING LOGS
* use ```wevtutil el``` command to display a list of event logs
* use ```wevtutil cl [log name]``` command to clear specific logs (eg: system, security, application etc)
* to delete a file in such a way that recovery is impossible, use command: ```cipher /w:[drive/folder location]```
Various scripts are available that wipe logs just by running them with administor privileges

## CLEARING LINUX LOGS
* run command ```export HISTSIZE=0``` to disable the BASH shell from saving command history.
* run command ```history -c``` to clear the stored history.
* run command ```history -w``` to clear the history of only the current shell.
* run command ```shred ~/.bash_history``` to irrecoverably delete the bash history.
