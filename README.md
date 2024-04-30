
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


## OUTPUT:
![318633603-584a6e38-f7f5-48d1-a794-e46919e7f8d8](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/f29c0c9d-3a29-415b-a2cf-36775f4a3e38)


Invoke msfconsole:
![318633708-8ece81bd-8d91-498d-91cc-18096809bf40](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/51f1c869-68dc-44e4-bad8-5f76f405f482)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![318633750-6d8173b7-464c-4be9-9c3c-075633e02d2b](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/08c6f323-2fd6-4415-bdd6-cc3f09751995)

Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
OUTPUT:
![318633849-ff252e3e-fe1e-4a93-b754-5d4ced4f68b7](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/f2a7e113-9cc7-4a08-a5ab-47b6dc35ecbf)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
OUTPUT:
![318633950-3ee66371-ccc9-4245-b5ff-5356809e362c](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/b6e80768-1519-4bf0-b228-52154fc7f636)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

OUTPUT:
![318634104-93452bc1-249d-4a05-bda6-140c2db75eea](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/f0449365-a1fa-4372-a5e2-a60a64ca1a83)# Metasploit-for-reconnaissance

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

OUTPUT:
![318634049-97a56fd6-c08c-43d3-8816-6a1fcef38c56](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/7f22c9d3-5d94-4c7a-bf13-37d9b6d97f74)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![318634104-93452bc1-249d-4a05-bda6-140c2db75eea](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/23a42c7a-bbb5-42e3-a695-6ea655ab5408)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![318634296-41895fb8-8adf-4e5d-a486-0bb7cfda2f8c](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/2d6b5655-f6b2-48ee-a7ea-3e8351efe49f)


use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

Use the set rhosts command to set the parameter and run the module, as follows:

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![318634349-e3a3574e-8c7e-4148-9cf5-5064b270f690](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/26f11bdb-a652-4c6b-81b8-c59abbee63cb)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![318634402-671d8b95-a4c4-4be3-a006-52c6dccf5803](https://github.com/pavankishore-AIDS/Metasploit-for-reconnaissance/assets/94154941/28a2fb5f-8cf1-449a-a18b-68055506bf19)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
