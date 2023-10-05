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
![p1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/c0fa3508-77b3-47aa-a401-1d03333ecf56)


Invoke msfconsole:


## OUTPUT:
![p2](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/cb2f9a85-3a12-487b-a4d5-9ac830d50aeb)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![U1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/747f30db-a30b-4794-8d12-9c167d6485f7)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![U2](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/293feea8-a331-4db5-a140-13d93e1ddccf)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![V1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/bdd8b772-adc1-489a-8e6f-961760712ada)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![O1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/8ca84c61-8854-4c0a-96a6-c6db5b98789b)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

## OUTPUT:
![S1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/5f2facfa-36ed-4854-9018-f9872f434641)

The info command provides information regarding a module or platform,

## OUTPUT :
![L1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/b2b0b27f-1de6-43db-8d59-4d942db7481c)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:
![Y1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/4309708e-96ad-465b-ac93-02ae931b343b)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

## OUTPUT:
![J1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/c7cedee7-8123-4de5-8277-f87ad3621637)

use 11 Or: use auxiliary/scanner/mysql/mysql_version
## OUTPUT:
![B1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/3ff8f60a-3bcf-4e78-8b07-78250ab2e304)

Use the set rhosts command to set the parameter and run the module, as follows:

## OUTPUT:
![G1](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/330b5431-a82f-4753-adcd-41340a26a944)


After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

## OUTPUT:
![AV](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/f0859057-a9a7-4a3c-8354-f8071c6ae330)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

## OUTPUT:
![FF](https://github.com/Sharmilasha/Metasploit-for-reconnaissance/assets/94506182/ca08ee48-9935-4999-9c9e-95ffe9c17099)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
