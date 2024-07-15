---
title: Nmap_command
description: Nmap_command
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 216
#unlisted: true
---
* 
{:toc}

```markdown
# Comprehensive Nmap Commands

## Basic Scanning Techniques

### TCP SYN Scan (Default)
```bash
nmap -sS target
```
Example: `nmap -sS 192.168.1.1`

### TCP Connect Scan
```bash
nmap -sT target
```
Example: `nmap -sT 10.0.0.1`

### UDP Scan
```bash
nmap -sU target
```
Example: `nmap -sU 172.16.0.1`

### TCP ACK Scan
```bash
nmap -sA target
```
Example: `nmap -sA 192.168.0.1`

### TCP Window Scan
```bash
nmap -sW target
```
Example: `nmap -sW 10.10.10.1`

### TCP Null Scan
```bash
nmap -sN target
```
Example: `nmap -sN 192.168.10.1`

### TCP FIN Scan
```bash
nmap -sF target
```
Example: `nmap -sF 172.16.10.1`

### TCP Xmas Scan
```bash
nmap -sX target
```
Example: `nmap -sX 10.0.0.10`

### IP Protocol Scan
```bash
nmap -sO target
```
Example: `nmap -sO 192.168.1.1`

## Advanced Scanning Techniques

### Service Version Detection
```bash
nmap -sV target
```
Example: `nmap -sV 10.0.0.1`

### OS Detection
```bash
nmap -O target
```
Example: `nmap -O 172.16.0.1`

### Aggressive Scan
```bash
nmap -A target
```
Example: `nmap -A 192.168.0.1`

### Script Scanning
```bash
nmap -sC target
```
Example: `nmap -sC 10.10.10.1`

### Traceroute
```bash
nmap --traceroute target
```
Example: `nmap --traceroute 192.168.10.1`

### Scan using IPv6
```bash
nmap -6 target
```
Example: `nmap -6 fe80::1`

### Scan specific ports
```bash
nmap -p port1,port2,port3 target
```
Example: `nmap -p 80,443 172.16.10.1`

### Scan all ports (TCP)
```bash
nmap -p- target
```
Example: `nmap -p- 10.0.0.10`

### Scan all ports (UDP)
```bash
nmap -p- -sU target
```
Example: `nmap -p- -sU 192.168.1.1`

### Scan using a list of hosts
```bash
nmap -iL hosts.txt
```
Example: `nmap -iL targets.txt`

## Output Options

### Normal Output
```bash
nmap -oN output.txt target
```
Example: `nmap -oN scan_results.txt 10.0.0.1`

### XML Output
```bash
nmap -oX output.xml target
```
Example: `nmap -oX scan_results.xml 172.16.0.1`

### Grepable Output
```bash
nmap -oG output.grep target
```
Example: `nmap -oG scan_results.grep 192.168.0.1`

### All formats (Normal, XML, Grepable)
```bash
nmap -oA output target
```
Example: `nmap -oA scan_results 10.10.10.1`

## Firewall Evasion Techniques

### Fragment Packets
```bash
nmap -f target
```
Example: `nmap -f 192.168.10.1`

### Decoy Scan
```bash
nmap -D RND:10 target
```
Example: `nmap -D RND:10 172.16.10.1`

### Idle Scan
```bash
nmap -sI zombie target
```
Example: `nmap -sI 10.0.0.10`

### Source Port Manipulation
```bash
nmap --source-port port target
```
Example: `nmap --source-port 12345 192.168.1.1`

## Timing and Performance

### Timing Templates
```bash
nmap -T<0-5> target
```
Example: `nmap -T4 10.0.0.1`

### Set Scan Delay
```bash
nmap --scan-delay time target
```
Example: `nmap --scan-delay 5s 172.16.0.1`

### Parallel Host/Port Scanning
```bash
nmap -Pn -n -T4 -p- --min-rate 1000 target
```
Example: `nmap -Pn -n -T4 -p- --min-rate 1000 192.168.0.1`

## Miscellaneous

### Scan for DDOS Reflection
```bash
nmap --ddos target
```
Example: `nmap --ddos 10.10.10.1`

### Network Distance (Hop Count)
```bash
nmap --max-rtt-timeout 200ms --max-retries 1 target
```
Example: `nmap --max-rtt-timeout 200ms --max-retries 1 192.168.10.1`

### Save packets to PCAP file
```bash
nmap -oX - -sP target
```
Example: `nmap -oX - -sP 172.16.10.1`

### Scan using SSL/TLS
```bash
nmap --ssl target
```
Example: `nmap --ssl 10.0.0.10`

### Show Host Interfaces and Routes
```bash
nmap --iflist
```
Example: `nmap --iflist`

### List Nmap Script Categories
```bash
nmap --script-help all
```
Example: `nmap --script-help all`

### ARP Ping Scan
```bash
nmap -PR target
```
Example: `nmap -PR 192.168.1.1`

### Scan using MAC Address
```bash
nmap --spoof-mac MAC target
```
Example: `nmap --spoof-mac 00:11:22:33:44:55 10.0.0.1`

### Output IP addresses only
```bash
nmap -sL target
```
Example: `nmap -sL 172.16.0.1`

## Nmap Scripting Engine (NSE)

### List available NSE scripts
```bash
nmap --script-help *
```
Example: `nmap --script-help *`

### Run a specific NSE script
```bash
nmap --script scriptname target
```
Example: `nmap --script http-enum.nse 192.168.0.1`

### Run multiple NSE scripts
```bash
nmap --script "script1,script2" target
```
Example: `nmap --script "ftp*,smb*" 10.10.10.1`

### Run NSE scripts against all ports
```bash
nmap --script "script" -p- target
```
Example: `nmap --script "vuln" -p- 192.168.10.1`

### Run NSE scripts using a script alias
```bash
nmap --script vuln target
```
Example: `nmap --script vuln 172.16.10.1`

## Help and Miscellaneous

### Display Nmap version and options
```bash
nmap -v
```
Example: `nmap -v`

### Display Nmap help menu
```bash
nmap -h
```
Example: `nmap -h`

### Update Nmap scripts database
```bash
nmap --script-updatedb
```
Example: `nmap --script-updatedb`

```

This Markdown document now includes examples for each command and also includes sections specifically for Nmap Scripting Engine (NSE) commands, demonstrating how to list scripts, run specific scripts, run scripts against all ports, and more. Adjust the examples and commands as needed for your specific scanning and reconnaissance tasks using Nmap.

