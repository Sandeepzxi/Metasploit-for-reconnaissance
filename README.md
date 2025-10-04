# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

## OUTPUT:

<img width="723" height="346" alt="image" src="https://github.com/user-attachments/assets/2f5f3b96-6841-4055-a0da-c3819f56ae2e" />

Invoke msfconsole:

## OUTPUT:
<img width="650" height="561" alt="image" src="https://github.com/user-attachments/assets/e21afca7-07a6-4536-93c9-856b542e5004" />

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:

<img width="816" height="796" alt="image" src="https://github.com/user-attachments/assets/c673ffef-ee5a-4ba1-934b-b3807c054d4d" />

Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).
msf >  nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

<img width="682" height="439" alt="image" src="https://github.com/user-attachments/assets/9b15166b-3e85-45a9-a17d-5a15c04cca27" />



use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows.
msf > db_nmap 192.168.181.0/24
## OUTPUT:
<img width="790" height="437" alt="image" src="https://github.com/user-attachments/assets/746bc2ae-8ba2-4508-8157-fdb23b9a65e3" />

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules.
cd /usr/share /metasploit-framework/modules/auxiliary
kali > ls -l
## OUTPUT:


Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit
## OUTPUT:
<img width="1796" height="776" alt="image" src="https://github.com/user-attachments/assets/7677f87a-a5a1-4120-a10d-69b7c479aaa0" />

The info command provides information regarding a module or platform
## OUTPUT:
<img width="912" height="787" alt="image" src="https://github.com/user-attachments/assets/4ac7ee4e-db56-4895-90fb-8fcb155ad362" />

<img width="810" height="542" alt="image" src="https://github.com/user-attachments/assets/a4f0e486-fd7a-4c55-8454-fa05178994b3" />

## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.
db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
## OUTPUT:
<img width="1057" height="160" alt="image" src="https://github.com/user-attachments/assets/e222cfb8-a3fe-43f9-a378-1c6393dc0259" />

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database.
search type:auxiliary mysql
## OUTPUT:
<img width="1422" height="441" alt="image" src="https://github.com/user-attachments/assets/55bc7c8f-436d-4fa8-bdac-789665c77ad2" />

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details.
use 11
## OUTPUT:
<img width="1141" height="384" alt="image" src="https://github.com/user-attachments/assets/0e5e4f2e-2635-4bda-8108-b16fc1df2b52" />

Use the set rhosts command to set the parameter and run the module, as follows:

## OUTPUT:
<img width="532" height="85" alt="image" src="https://github.com/user-attachments/assets/e099654d-e1eb-4135-931e-f50196447845" />

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

## OUTPUT:
<img width="1241" height="503" alt="image" src="https://github.com/user-attachments/assets/bd98f553-c31a-45f6-99ca-a7b562010cb0" />

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
