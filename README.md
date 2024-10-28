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
![image](https://github.com/user-attachments/assets/d45558a8-de7c-48b0-bdb3-c3be9d8bb34e)

Invoke msfconsole:
![image](https://github.com/user-attachments/assets/12558769-b311-4752-a310-0dea9b5eb032)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/user-attachments/assets/8ead3a2b-708a-456b-bb97-ba05a14431af)

## Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000


## OUTPUT:
![image](https://github.com/user-attachments/assets/43fc36c1-8e2f-4a67-9427-515d81633114)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![image](https://github.com/user-attachments/assets/c2209992-fe6a-4b7f-8009-a539935919e1)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![image](https://github.com/user-attachments/assets/814d5660-7ec2-4763-97e5-cb26f11b3949)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

## OUTPUT:
![image](https://github.com/user-attachments/assets/b6599ca2-6887-4989-af02-20fec4169075)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/user-attachments/assets/e3145a1b-3497-4a82-8c61-9c37060c99c7)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/user-attachments/assets/cf91687d-b931-4df7-91dc-7dd9f63262d1)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/user-attachments/assets/83169378-7ea8-4dc9-b9d7-15e700950b89)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/user-attachments/assets/5ba398c3-5bee-4c33-8237-8610b7680508)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/user-attachments/assets/eb8a2666-ae78-42fd-b405-02f91dee68d0)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/user-attachments/assets/c2fbc108-93dd-4616-a410-be20449ff9bf)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
