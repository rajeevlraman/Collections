---
title: IT Admin tools on a stick
description: IT Admin tools on a stick
layout: libdoc/page

#LibDoc specific below
category: Troubleshooting
order: 90
#unlisted: true
---
* 
{:toc}
Having a USB toolkit loaded with essential tools can be invaluable for a Network Admin, IT Support professional, and Ethical Hacker. Here's a comprehensive list of tools categorized by purpose, along with descriptions and typical use cases.


## Network Admin and IT Support Tools

### System Utilities

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Hiren's BootCD**        | A comprehensive bootable toolkit with various repair tools      | System recovery, password reset, disk partitioning            | [Hiren's BootCD](https://www.hirensbootcd.org/) |
| **Ultimate Boot CD (UBCD)**| Bootable disk with hardware diagnostics and recovery tools      | Hardware diagnostics, system rescue                          | [UBCD](https://www.ultimatebootcd.com/)         |
| **Rufus**                 | Utility to create bootable USB drives                            | Creating bootable USBs for OS installations and tools        | [Rufus](https://rufus.ie/)                      |

### Network Diagnostics

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Wireshark**             | Network protocol analyzer and packet sniffer                    | Analyzing network traffic, troubleshooting network issues    | [Wireshark](https://www.wireshark.org/)         |
| **Nmap**                  | Network scanner for discovering hosts and services              | Network discovery, security auditing                         | [Nmap](https://nmap.org/)                       |
| **Angry IP Scanner**      | Fast and friendly network scanner                               | Scanning and mapping IP addresses on a network               | [Angry IP Scanner](https://angryip.org/)        |
| **TCPdump**               | Command-line packet analyzer                                   | Capturing and analyzing network traffic                      | [TCPdump](https://www.tcpdump.org/)             |
| **Netcat (nc)**           | Utility for reading and writing data across network connections | Debugging network connections, testing open ports            | [Netcat](http://netcat.sourceforge.net/)        |
| **iperf3**                | Network bandwidth measurement tool                             | Testing network throughput and performance                   | [iperf3](https://iperf.fr/)                     |

### System Monitoring and Management

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Process Explorer**      | Advanced task manager for Windows                               | Monitoring system processes, identifying malware             | [Process Explorer](https://docs.microsoft.com/en-us/sysinternals/downloads/process-explorer) |
| **CPU-Z**                 | Tool for detailed system information                            | Checking CPU, memory, and motherboard specifications         | [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html) |
| **HWMonitor**             | Hardware monitoring tool                                        | Monitoring system temperatures, voltages, and fan speeds     | [HWMonitor](https://www.cpuid.com/softwares/hwmonitor.html) |
| **Speccy**                | Detailed system information tool                                | Viewing detailed hardware and system specifications          | [Speccy](https://www.ccleaner.com/speccy)        |
| **Sysinternals Suite**    | Collection of Windows utilities                                 | Various tasks including process management and disk usage    | [Sysinternals Suite](https://docs.microsoft.com/en-us/sysinternals/downloads/sysinternals-suite) |

### Disk Management and Recovery

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **GParted**               | Free partition editor for graphically managing disk partitions  | Creating, deleting, resizing, and moving partitions          | [GParted](https://gparted.org/)                 |
| **Clonezilla**            | Open-source disk cloning and imaging tool                       | System backup, recovery, and deployment                      | [Clonezilla](https://clonezilla.org/)           |
| **TestDisk**              | Data recovery software for lost partitions and files            | Recovering lost partitions and repairing corrupt file systems| [TestDisk](https://www.cgsecurity.org/wiki/TestDisk) |
| **Recuva**                | File recovery software for Windows                              | Recovering deleted files from hard drives and memory cards   | [Recuva](https://www.ccleaner.com/recuva)       |

### Security and Maintenance

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Malwarebytes**          | Anti-malware software                                           | Scanning and removing malware from systems                   | [Malwarebytes](https://www.malwarebytes.com/)   |
| **CCleaner**              | System optimization and cleaning tool                           | Removing unnecessary files, managing startup programs        | [CCleaner](https://www.ccleaner.com/)           |
| **Belarc Advisor**        | Detailed system audit tool                                      | Generating system profiles with hardware and software details| [Belarc Advisor](https://www.belarc.com/products_belarc_advisor) |
| **BitLocker To Go**       | Encryption tool for securing data on USB drives                 | Encrypting USB drives to protect sensitive data              | [BitLocker](https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-to-go-faq) |



## Ethical Hacker Tools

### Network Scanning and Enumeration

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Nmap**                  | Network scanner for discovering hosts and services              | Port scanning, network discovery                             | [Nmap](https://nmap.org/)                       |
| **Netcat (nc)**           | Utility for reading and writing data across network connections | Network diagnostics, banner grabbing                         | [Netcat](http://netcat.sourceforge.net/)        |
| **Fping**                 | Ping tool for scanning large networks quickly                   | Checking the availability of multiple hosts                  | [Fping](https://fping.org/)                     |
| **Unicornscan**           | Asynchronous network scanning tool                              | High-speed port scanning and service enumeration             | [Unicornscan](http://unicornscan.org/)          |

### Vulnerability Assessment

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **OpenVAS**               | Open-source vulnerability scanner                               | Scanning and identifying vulnerabilities in systems          | [OpenVAS](https://www.openvas.org/)             |
| **Nessus**                | Comprehensive vulnerability assessment tool                     | Vulnerability scanning and risk assessment                   | [Nessus](https://www.tenable.com/products/nessus) |
| **Nikto**                 | Web server scanner for potential vulnerabilities                | Scanning web servers for known vulnerabilities               | [Nikto](https://cirt.net/Nikto2)                |

### Exploitation Tools

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Metasploit Framework**  | Penetration testing platform for developing and executing exploits | Exploit development, payload generation, vulnerability assessment | [Metasploit](https://www.metasploit.com/)      |
| **BeEF**                  | Browser Exploitation Framework for web-based attacks             | Exploiting browser vulnerabilities, conducting phishing attacks| [BeEF](https://beefproject.com/)               |
| **Hydra**                 | Fast and flexible network logon cracker                         | Brute force attacks on various protocols and services        | [Hydra](https://github.com/vanhauser-thc/thc-hydra) |

### Wireless Security

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Aircrack-ng**           | Suite of tools for auditing wireless networks                   | Cracking WEP/WPA-PSK keys, capturing and analyzing packets    | [Aircrack-ng](https://www.aircrack-ng.org/)     |
| **Kismet**                | Wireless network detector and sniffer                          | Discovering and analyzing wireless networks                  | [Kismet](https://kismetwireless.net/)           |
| **WiFi Pineapple**        | Wireless auditing tool with various hacking capabilities       | Conducting Wi-Fi penetration tests and network assessments   | [WiFi Pineapple](https://www.wifipineapple.com/)|

### Password Cracking

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **John the Ripper**       | Fast password cracker for Unix, Windows, and other systems      | Cracking password hashes for various algorithms              | [John the Ripper](https://www.openwall.com/john/)|
| **Hashcat**               | Advanced password recovery tool                                 | Cracking complex password hashes using GPUs                  | [Hashcat](https://hashcat.net/hashcat/)         |
| **Cain & Abel**           | Password recovery and cracking tool for Windows                 | Recovering passwords from network packets, cracking hashes   | [Cain & Abel](https://www.oxid.it/cain.html)    |

### Forensics and Reverse Engineering

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Autopsy**               | Digital forensics platform                                      | Analyzing disk images, recovering deleted files              | [Autopsy](https://www.sleuthkit.org/autopsy/)   |


### Forensics and Reverse Engineering (continued)

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Volatility**            | Memory forensics framework                                      | Analyzing volatile memory for malware and artifacts          | [Volatility](https://www.volatilityfoundation.org/) |
| **IDA Pro**               | Disassembler for analyzing binary programs                      | Reverse engineering, debugging binaries                      | [IDA Pro](https://www.hex-rays.com/products/ida/) |
| **Ghidra**                | Software reverse engineering framework                          | Analyzing and understanding malware and software              | [Ghidra](https://ghidra-sre.org/)                |

### Monitoring and Logging

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Splunk**                | Platform for searching, monitoring, and analyzing machine-generated data | Log analysis, security information and event management  | [Splunk](https://www.splunk.com/)               |
| **ELK Stack (Elasticsearch, Logstash, Kibana)** | Open-source log management and analytics platform         | Centralized logging, log analysis, real-time monitoring     | [ELK Stack](https://www.elastic.co/what-is/elk-stack) |
| **Security Onion**        | Open-source network security monitoring and intrusion detection system | Network traffic analysis, log management, intrusion detection | [Security Onion](https://securityonion.net/)    |

### Virtualization and Containerization

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **VirtualBox**            | Cross-platform virtualization application                       | Running VMs for testing and development                      | [VirtualBox](https://www.virtualbox.org/)       |
| **Docker**                | Containerization platform                                       | Packaging applications and dependencies into containers      | [Docker](https://www.docker.com/)               |
| **Kubernetes**            | Container orchestration platform                                | Deploying, scaling, and managing containerized applications  | [Kubernetes](https://kubernetes.io/)            |

### Miscellaneous

| Tool                      | Description                                                      | Use Case                                                     | URL                                             |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|
| **Putty**                 | SSH and telnet client                                           | Remote access to servers and networking devices              | [Putty](https://www.putty.org/)                 |
| **FileZilla**             | FTP, FTPS, and SFTP client                                      | Transferring files between systems securely                  | [FileZilla](https://filezilla-project.org/)     |
| **WinSCP**                | SFTP and FTP client for Windows                                 | Securely transferring files between local and remote systems | [WinSCP](https://winscp.net/eng/index.php)     |
| **TrueCrypt**             | Disk encryption software (deprecated, use VeraCrypt)            | Encrypting sensitive data on storage devices                 | [TrueCrypt](https://www.grc.com/misc/truecrypt/truecrypt.htm) |
| **VeraCrypt**             | Disk encryption software                                        | Encrypting disks and creating encrypted containers           | [VeraCrypt](https://www.veracrypt.fr/en/Home.html) |



### Considerations

- **Portability**: Ensure the tools you choose are portable and can run directly from a USB drive without installation.
  
- **Legal and Ethical Use**: Use ethical hacking tools responsibly and within legal boundaries. Ensure you have proper authorization before using them on networks or systems you don't own or manage.

- **Regular Updates**: Keep your toolkit updated with the latest versions of tools and utilities to ensure compatibility and security.

Having these tools readily accessible on a USB drive will empower you to handle a wide range of tasks, from network diagnostics and system management to security assessments and troubleshooting, whether you're in the field, in an office, or responding to emergencies.
