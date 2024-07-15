---
title: Nmap
description: Nmap
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 212
#unlisted: true
---
* 
{:toc}


# Comprehensive Nmap Commands

## Basic Scanning Techniques

| **Command**                   | **Description**                           | **Example**                          |
|-------------------------------|-------------------------------------------|--------------------------------------|
| `nmap -sS target`             | TCP SYN Scan (Default)                    | `nmap -sS 192.168.1.1`               |
| `nmap -sT target`             | TCP Connect Scan                          | `nmap -sT 10.0.0.1`                  |
| `nmap -sU target`             | UDP Scan                                  | `nmap -sU 172.16.0.1`                |
| `nmap -sA target`             | TCP ACK Scan                              | `nmap -sA 192.168.0.1`               |
| `nmap -sW target`             | TCP Window Scan                           | `nmap -sW 10.10.10.1`                |
| `nmap -sN target`             | TCP Null Scan                             | `nmap -sN 192.168.10.1`              |
| `nmap -sF target`             | TCP FIN Scan                              | `nmap -sF 172.16.10.1`               |
| `nmap -sX target`             | TCP Xmas Scan                             | `nmap -sX 10.0.0.10`                 |
| `nmap -sO target`             | IP Protocol Scan                          | `nmap -sO 192.168.1.1`               |

## Advanced Scanning Techniques

| **Command**                   | **Description**                           | **Example**                          |
|-------------------------------|-------------------------------------------|--------------------------------------|
| `nmap -sV target`             | Service Version Detection                 | `nmap -sV 10.0.0.1`                  |
| `nmap -O target`              | OS Detection                              | `nmap -O 172.16.0.1`                 |
| `nmap -A target`              | Aggressive Scan                           | `nmap -A 192.168.0.1`                |
| `nmap -sC target`             | Script Scanning                           | `nmap -sC 10.10.10.1`                |
| `nmap --traceroute target`    | Traceroute                                | `nmap --traceroute 192.168.10.1`     |
| `nmap -6 target`              | Scan using IPv6                           | `nmap -6 fe80::1`                    |
| `nmap -p port1,port2,port3 target` | Scan specific ports                  | `nmap -p 80,443 172.16.10.1`         |
| `nmap -p- target`             | Scan all ports (TCP)                      | `nmap -p- 10.0.0.10`                 |
| `nmap -p- -sU target`         | Scan all ports (UDP)                      | `nmap -p- -sU 192.168.1.1`           |
| `nmap -iL hosts.txt`          | Scan using a list of hosts                | `nmap -iL targets.txt`               |

## Output Options

| **Command**                   | **Description**                           | **Example**                          |
|-------------------------------|-------------------------------------------|--------------------------------------|
| `nmap -oN output.txt target`  | Normal Output                             | `nmap -oN scan_results.txt 10.0.0.1` |
| `nmap -oX output.xml target`  | XML Output                                | `nmap -oX scan_results.xml 172.16.0.1`|
| `nmap -oG output.grep target` | Grepable Output                           | `nmap -oG scan_results.grep 192.168.0.1`|
| `nmap -oA output target`      | All formats (Normal, XML, Grepable)       | `nmap -oA scan_results 10.10.10.1`   |

## Firewall Evasion Techniques

| **Command**                   | **Description**                           | **Example**                          |
|-------------------------------|-------------------------------------------|--------------------------------------|
| `nmap -f target`              | Fragment Packets                          | `nmap -f 192.168.10.1`               |
| `nmap -D RND:10 target`       | Decoy Scan                                | `nmap -D RND:10 172.16.10.1`         |
| `nmap -sI zombie target`      | Idle Scan                                 | `nmap -sI 10.0.0.10`                 |
| `nmap --source-port port target` | Source Port Manipulation               | `nmap --source-port 12345 192.168.1.1`|

## Timing and Performance

| **Command**                   | **Description**                           | **Example**                          |
|-------------------------------|-------------------------------------------|--------------------------------------|
| `nmap -T<0-5> target`         | Timing Templates                          | `nmap -T4 10.0.0.1`                  |
| `nmap --scan-delay time target`| Set Scan Delay                            | `nmap --scan-delay 5s 172.16.0.1`    |
| `nmap -Pn -n -T4 -p- --min-rate 1000 target` | Parallel Host/Port Scanning   | `nmap -Pn -n -T4 -p- --min-rate 1000 192.168.0.1`|

## Miscellaneous

| **Command**                   | **Description**                           | **Example**                          |
|-------------------------------|-------------------------------------------|--------------------------------------|
| `nmap --ddos target`          | Scan for DDOS Reflection                  | `nmap --ddos 10.10.10.1`             |
| `nmap --max-rtt-timeout 200ms --max-retries 1 target` | Network Distance (Hop Count) | `nmap --max-rtt-timeout 200ms --max-retries 1 192.168.10.1`|
| `nmap -oX - -sP target`       | Save packets to PCAP file                 | `nmap -oX - -sP 172.16.10.1`         |
| `nmap --ssl target`           | Scan using SSL/TLS                        | `nmap --ssl 10.0.0.10`               |
| `nmap --iflist`               | Show Host Interfaces and Routes           | `nmap --iflist`                      |
| `nmap --script-help all`      | List Nmap Script Categories               | `nmap --script-help all`             |
| `nmap -PR target`             | ARP Ping Scan                             | `nmap -PR 192.168.1.1`               |
| `nmap --spoof-mac MAC target` | Scan using MAC Address                    | `nmap --spoof-mac 00:11:22:33:44:55 10.0.0.1`|
| `nmap -sL target`             | Output IP addresses only                  | `nmap -sL 172.16.0.1`                |

## Nmap Scripting Engine (NSE)

| **Command**                   | **Description**                           | **Example**                          |
|-------------------------------|-------------------------------------------|--------------------------------------|
| `nmap --script-help *`        | List available NSE scripts                | `nmap --script-help *`               |
| `nmap --script scriptname target` | Run a specific NSE script              | `nmap --script http-enum.nse 192.168.0.1`|
| `nmap --script "script1,script2" target` | Run multiple NSE scripts         | `nmap --script "ftp*,smb*" 10.10.10.1`|
| `nmap --script "script" -p- target` | Run NSE scripts against all ports    | `nmap --script "vuln" -p- 192.168.10.1`|
| `nmap --script vuln target`   | Run NSE scripts using a script alias     | `nmap --script vuln 172.16.10.1`    |

## Help and Miscellaneous

| **Command**                   | **Description**                           | **Example**                          |
|-------------------------------|-------------------------------------------|--------------------------------------|
| `nmap -v`                     | Display Nmap version and options          | `nmap -v`                            |
| `nmap -h`                     | Display Nmap help menu                    | `nmap -h`                            |
| `nmap --script-updatedb`      | Update Nmap scripts database              | `nmap --script-updatedb`             |
```

This format keeps each command, its description, and an example all in one row for clarity and easy reference. Adjust the examples as needed based on your specific use case and target environment.
