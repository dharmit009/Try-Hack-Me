# Basics of networking 

Your computer opens multiple ports when talking to multiple sites lets say you have 2 tabs open 

1. google.com which might be connected to port 1234 on your local machine. 

1. duckduckgo.com which might be connected to port 1233 on your local machine. 

*Note:* The port through which the server is connected might be standardized or custom. i.e for https it mainly uses 8080 or 443.

> *Every computer has a total of 65535 available ports*

## Standard Ports: 

Here are some of the standard ports. 

* HTTP    80
* HTTPS   443
* NETBIOS 139
* SMB     445

## What is Port Scannning?

**Port Scanning** is a process of scanning individual ports on machine. In Port Scanning, we try to find open ports and information offered by that particular port by trying to connect to the computer. Once we have found the open ports and the service which it offers we try to find vulnerabilities or configuration flaws within the service itself and use it as an advantage to get access to the system. 

## What is nmap?

**nmap** stands for network mapper, It is a port scanning tool which allows us to scan for open ports. Nmap has become the industry standard for scanning ports as it provide very accurate results, it also offers features like vulnerability scanning, automating into scripts, custom scripts, pre-made / default scripts, OS guessing and much more. 

## Basic Scan using nmap

**TCP SCAN:**

`nmap -sT -T4 -p0-65535 <ip>`

Let us break this down a bit ... 

`nmap -sT -T4 -p0-65535 <ip or ip-range>`
  |    |   |   |        |
  |    |   |   |        |--> Perform everything on this ip or ip-range. 
  |    |   |   |--> Scan Ports 0 to 65535
  |    |   |--> Set Speed Of Scan = 4 out of 5. 
  |    | --> TCP SCAN. 
  |--> Network Mapper. 
  
  > *NOTE:* This is a basic nmap scan so the syntax may look a lot more different. The above example of a TCP scan. 

## How to run scripts?

All the scripts are written in `LUA` and are ranned by `NSE` **[ Nmap Script Engine ]**
The script reside in `/usr/share/nmap/script.db` you can *grep* the database if you want in order the right scripts. To run scripts we typically use the `--script` parameter. Let us say you want to enumerate the ftp server for enumeration then the command which you will run will look like `nmap -T4 -Pn -vv <ip> -p <ftp port> --script=ftp-anon`

In the similar way you can even run entire suite of categories if you need to enumerate everything in particular. For example you want to test for all vulnerabilities then you would typically do that by running `nmap -T4 -Pn -vv <ip> -p- --script=vuln` this will run all the script which has vulnerability as an category. 

You can even use script defaults by providing `-sC` or `--script=default`

## Types of NMAP Scans: 

1. `sX` - XMAS Scan - set XMAS flag to set in the TCP/IP packet. 
1. `sF` - FIN Scan  - set FIN flag to set in the TCP/IP packet. 
1. `sN` - NULL Scan - set NULL flag to set in the TCP/IP packet. 
1. `sS` - SYN Scan  - set SYN flag to set in the TCP/IP packet. 
1. `sT` - TCP Scan  - set SYN flag to set in the TCP/IP packet. 

## Firewall envasion techniques:

`--mtu <val>` - How many fragment packets to send at once. 
