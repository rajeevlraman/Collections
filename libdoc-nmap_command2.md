---
title: nmap_command2
description: nmap_command2
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 218
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

### TCP Connect Scan
```bash
nmap -sT target
```

### UDP Scan
```bash
nmap -sU target
```

### TCP ACK Scan
```bash
nmap -sA target
```

### TCP Window Scan
```bash
nmap -sW target
```

### TCP Null Scan
```bash
nmap -sN target
```

### TCP FIN Scan
```bash
nmap -sF target
```

### TCP Xmas Scan
```bash
nmap -sX target
```

### IP Protocol Scan
```bash
nmap -sO target
```

## Advanced Scanning Techniques

### Service Version Detection
```bash
nmap -sV target
```

### OS Detection
```bash
nmap -O target
```

### Aggressive Scan
```bash
nmap -A target
```

### Script Scanning
```bash
nmap -sC target
```

### Traceroute
```bash
nmap --traceroute target
```

### Scan using IPv6
```bash
nmap -6 target
```

### Scan specific ports
```bash
nmap -p port1,port2,port3 target
```

### Scan all ports (TCP)
```bash
nmap -p- target
```

### Scan all ports (UDP)
```bash
nmap -p- -sU target
```

### Scan using a list of hosts
```bash
nmap -iL hosts.txt
```

## Output Options

### Normal Output
```bash
nmap -oN output.txt target
```

### XML Output
```bash
nmap -oX output.xml target
```

### Grepable Output
```bash
nmap -oG output.grep target
```

### All formats (Normal, XML, Grepable)
```bash
nmap -oA output target
```

## Firewall Evasion Techniques

### Fragment Packets
```bash
nmap -f target
```

### Decoy Scan
```bash
nmap -D RND:10 target
```

### Idle Scan
```bash
nmap -sI zombie target
```

### Source Port Manipulation
```bash
nmap --source-port port target
```

## Timing and Performance

### Timing Templates
```bash
nmap -T<0-5> target
```

### Set Scan Delay
```bash
nmap --scan-delay time target
```

### Parallel Host/Port Scanning
```bash
nmap -Pn -n -T4 -p- --min-rate 1000 target
```

## Miscellaneous

### Scan for DDOS Reflection
```bash
nmap --ddos target
```

### Network Distance (Hop Count)
```bash
nmap --max-rtt-timeout 200ms --max-retries 1 target
```

### Save packets to PCAP file
```bash
nmap -oX - -sP target
```

### Scan using SSL/TLS
```bash
nmap --ssl target
```

### Show Host Interfaces and Routes
```bash
nmap --iflist
```

### List Nmap Script Categories
```bash
nmap --script-help all
```

### ARP Ping Scan
```bash
nmap -PR target
```

### Scan using MAC Address
```bash
nmap --spoof-mac MAC target
```

### Output IP addresses only
```bash
nmap -sL target
```

## Help and Miscellaneous

### Display Nmap version and options
```bash
nmap -v
```

### Display Nmap help menu
```bash
nmap -h
```

### Update Nmap scripts database
```bash
nmap --script-updatedb
```

```

This expanded Markdown document now includes additional categories such as ARP Ping Scan, Scan using MAC Address, Output IP addresses only, Show Host Interfaces and Routes, List Nmap Script Categories, and more. Adjust the commands based on specific needs and environments for comprehensive Nmap scanning and reconnaissance tasks.
