---
title: Ncap
description: Ncap
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 212
#unlisted: true
---
* 
{:toc}

### ncap Description

**ncap** is a command-line tool used for capturing and analyzing network packets. It is part of the Nmap suite of network security tools and provides features for capturing packets from network interfaces, performing offline analysis on captured packet files, and exporting captured data in various formats.

### ncap Use

- **Packet Capture:** ncap can capture packets from network interfaces in real-time.
- **Offline Analysis:** It can analyze previously captured packet files (.pcap format).
- **Filtering and Processing:** ncap supports packet filtering based on various criteria.
- **Exporting Data:** Captured packets can be exported in different formats for further analysis.

### ncap Commands and Examples

| **Command**                    | **Description**                                                                 | **Example**                                                                                   |
|--------------------------------|---------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| `ncap -i <interface>`          | Start capturing packets from the specified network interface.                   | `ncap -i eth0`                                                                                |
| `ncap -r <file.pcap>`          | Read and analyze packets from a captured file (.pcap format).                    | `ncap -r capture.pcap`                                                                        |
| `ncap -s <filter>`             | Apply a capture filter to capture specific types of packets.                     | `ncap -i eth0 -s "host 192.168.1.100"`                                                        |
| `ncap -w <file.pcap>`          | Write captured packets to a file for offline analysis.                           | `ncap -i eth0 -w capture.pcap`                                                                |
| `ncap -o <output.txt>`         | Export captured packets to a file in ASCII format.                               | `ncap -r capture.pcap -o output.txt`                                                           |
| `ncap -P <protocol>`           | Specify a protocol (e.g., tcp, udp) to capture packets for specific protocols.    | `ncap -i eth0 -P tcp`                                                                         |
| `ncap -c <count>`              | Capture a specified number of packets and then stop.                             | `ncap -i eth0 -c 100`                                                                         |
| `ncap -v`                      | Verbose mode; display detailed information during packet capture.                | `ncap -i eth0 -v`                                                                             |
| `ncap -h`                      | Display help and usage information for ncap.                                      | `ncap -h`                                                                                     |

### Example Usage

1. **Capture packets on interface eth0:**
   ```
   ncap -i eth0
   ```

2. **Read packets from a captured file (capture.pcap):**
   ```
   ncap -r capture.pcap
   ```

3. **Capture packets with a filter (capture traffic from a specific IP address):**
   ```
   ncap -i eth0 -s "host 192.168.1.100"
   ```

4. **Write captured packets to a file (capture.pcap):**
   ```
   ncap -i eth0 -w capture.pcap
   ```

5. **Export captured packets to a text file (output.txt):**
   ```
   ncap -r capture.pcap -o output.txt
   ```

6. **Capture TCP packets only:**
   ```
   ncap -i eth0 -P tcp
   ```

7. **Capture a limited number of packets (e.g., 100 packets):**
   ```
   ncap -i eth0 -c 100
   ```

8. **Verbose mode for detailed capture information:**
   ```
   ncap -i eth0 -v
   ```

9. **Display help and usage information:**
   ```
   ncap -h
   ```

### Notes:
- Adjust `<interface>`, `<filter>`, `<file.pcap>`, `<output.txt>`, `<protocol>`, and `<count>` as per your specific requirements.
- Ensure proper permissions and administrative access to execute ncap commands and capture network packets.

This markdown guide provides a structured overview of ncap commands, descriptions, and examples for capturing and analyzing network packets effectively. Adjust the commands as necessary based on your network environment and requirements.
