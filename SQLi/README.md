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
```1' or 1=1 --```
![image](https://user-images.githubusercontent.com/56624593/151232264-d9dcd6b9-0205-4a89-b7cd-24205b761c0d.png)<br>
after we hit enter, we can see that we have succesfully logged in.<br>
![image](https://user-images.githubusercontent.com/56624593/151232426-d67c0af8-5640-480b-860b-efc1d9a8270a.png)<br>
we can similarly write a malicious SQL query to create a new user in the database
```1';insert into login values ('johndoe','password'); --```
![image](https://user-images.githubusercontent.com/56624593/151233357-255ec6f9-d5de-4283-96b0-c2f8e6b7fdf8.png)<br>
the new user named johndoe with password as password has been created<br>

### RCE USING SQLi
shell code can be executed on a server that is vulnerable to SQLi <br>
eg:<br>
```1';exec master..xp_cmdshell '<shell command>'; --```<br>
![image](https://user-images.githubusercontent.com/56624593/151235445-9e09e104-344a-402f-8de2-44e05a0f0660.png)
the shell command that is in the SQL query will be executed on the victim server
