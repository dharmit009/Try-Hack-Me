# Basics of networking 

Your computer opens multiple ports when talking to multiple sites lets say you have 2 tabs open 

1. google.com which might be connected to port 1234 on your local machine. 

1. duckduckgo.com which might be connected to port 1233 on your local machine. 

*Note:* The port through which the server is connected might be standardized or custom. i.e for https it mainly uses 8080 or 443.

> *Every computer has a total of 65535 available ports*


# Standard Ports: 

1. HTTP    80
1. HTTPS   443
1. NETBIOS 139
1. SMB     445

# How to run scripts?

All the scripts are written in LUA and are ranned by NSE [ Nmap Script Engine ]
The script reside in /usr/share/nmap/script.db you can grep the database if you want in order the right scripts. To run scripts we typically use the --script parameter. Let us say you want to enumerate the ftp server for enumeration then the command which you will run will look like `nmap -T4 -Pn -vv <ip> -p <ftp port> --script=ftp-anon`

In the similar way you can even run entire suite of categories if you need to enumerate everything in particular. for example you want to test for all vulnerabilities then you would typically do that by running `nmap -T4 -Pn -vv <ip> -p- --script=vuln` this will run all the script which has vulnerability as an category. 

You can even use script defaults by providing -sC or --script=default

## Types of NMAP Scans: 

1. XMAS Scan - sX - set XMAS flag to set in the TCP/IP packet. 
1. FIN Scan  - sF - set FIN flag to set in the TCP/IP packet. 
1. NULL Scan - sF - set NULL flag to set in the TCP/IP packet. 
1. SYN Scan  - sS - set SYN flag to set in the TCP/IP packet. 
1. TCP Scan  - sT - set SYN flag to set in the TCP/IP packet. 

## Firewall envasion techniques:

--mtu <val> send fragment packets. 
