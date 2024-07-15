---
title: ceh_prepare
description: ceh_prepare
layout: libdoc/page

#LibDoc specific below
category: Features
order: 94
#unlisted: true
---
* 
{:toc}

## Introduction



 Hello Hackers, In this blog I will be sharing my secret strategy on how I cleared my CEH (Certified Ethical Hacker) Practical exam in the first attempt. In the next 10 minutes, you will have a whole roadmap in front of you on what is CEH (Practical), who can take this exam and what are the things required to clear this exam along with my strategy.

Let’s start

The Certified Ethical Hacker (Practical) exam is a tough test that lasts for six hours. During this exam, you need to show how you can use ethical hacking methods to solve security problems within a limited time, just like in real situations. A group of experts, including people with a lot of experience, created this exam. They made 20 situations based on real life and asked questions about them. These questions check if you have the important skills needed for ethical hacking, like the ones you learn in the CEH program. This exam isn't a pretend one – it's like a real company's computer network. They use virtual machines, networks, and programs that work live to test your ethical hacking skills.

## Exam Details

- **Exam Title:** Certified Ethical Hacker (Practical)
- **Number of Practical Challenges:** 20
- **Exam Duration:** 6 hours
- **Exam Infrastructure:** iLabs (browser-based)
- **Exam Format:** iLabs Cyber Range
- **Passing Score:** 70% (14 Questions out of 20)
- **Certificate validity:** 3 years

## Course Content 

1. Unit 1: Introduction to Ethical Hacking
2. Unit 2: FootPrinting and Reconnaissance
3. Unit 3: Scanning Networks
4. Unit 4: Enumeration
5. Unit 5: Vulnerability Analysis
6. Unit 6: System Hacking
7. Unit 7: Malware Threats
8. Unit 8: Sniffing using Wireshark
9. Unit 9: Social Engineering
10. Unit 10: Denial-of-Service
11. Unit 12: Session Hijacking
12. Unit 13: Evading IDS, Firewalls, and Honeypots
13. Unit 14: Hacking Web Servers
14. Unit 15: Hacking Web Applications
15. Unit 16: SQL Injection
16. Unit 17: Hacking Wireless Networks
17. Unit 18: Hacking Mobile Platforms
18. Unit 19: IoT and OT Hacking
19. Unit 19: Cloud Computing
20. Unit 20: Cryptography

## How to enroll for CEH Practical?

- Go to the EC-Council official website and read through everything you need to know [here](https://www.eccouncil.org/train-certify/certified-ethical-hacker-ceh-practical/)
- **Create Account:** Create an account on EC-Council's Aspen portal.
- **Purchase Voucher:** Buy a CEH Practical exam voucher from the EC-Council or authorized centers. You can buy the voucher from the official store [here](https://store.eccouncil.org/product/ceh-practical-exam/).
- Or you can fill out the form from the official website and you will get the whole guide via call or text (I personally prefer this way as you can ask your doubts and they help us understand).
- **Schedule Exam:** Log in to Aspen, select an exam date, and schedule the exam.

## Exam Experience

I know this is the most awaited part. The exam is watched over by a person called a proctor. They use GoToMeeting, a program that sees and hears you through your computer. They'll also record what's on your screen during the whole exam. After your identity is verified, your exam starts.

The exam is on a website called iLab. You don't need to worry about taking pictures of your virtual machines (VMs).

You'll get two Operating systems to test things on. One is Parrot OS, and the other is Windows 7. No more Kali this time.

- You can DO use the internet for the exam. You can look things up, take notes on your computer, watch videos, and read blogs. But DON’T write notes by hand, talk to people, or make calls.
- Your exam computers won't have regular internet access. You need to use your web browser to access the internet.
- Start with the scanning part (NMAP Scan), since the scanning part takes some time, I moved on to other hacking questions.
- Scan all ports on IPs because default scripts might not catch smart configurations.
- Use custom word lists for each module. For brute-forcing, try "Hydra & Medusa."
- Practice hacking on an Android-based Hack The Box (HTB) box, as the coursework covers mobile hacking.
- If a challenge is too hard or time-consuming, move on and return later.
- Don't skip cryptography and steganography modules. Learn the basics.
- Reconnaissance and enumeration are crucial. Gather lots of details.
- Submit answers exactly as requested; prepopulated answers matter.
- Google is helpful, but avoid prying into personal matters!


# Study Guide

This is the main picture. I know you guys are excited about this. In my case, I had prior knowledge of basic Linux OS and some tools but don’t worry about it. This exam portion starts from basic and trains you till your potential to clear this exam.

If you have money, you can afford iLabs because the challenges are based on the iLab environment and you will get hands-on practice to clear this exam.

If you can’t afford iLab, there are many platforms in which you can practice the listed tools. I personally prefer TryHackMe and HackTheBox. This Exam is all about how much knowledge you have on tools.

## Tools

- Nmap
- Hydra
- Sqlmap
- Wpscan
- Nikto
- John
- Hashcat
- Metasploit
- Responder LLMNR
- Wireshark / tcpdump
- Steghide
- OpenStack
- QuickStego
- Dirb
- Searchsploit
- Crunch
- Cell
- Veracrypt
- Hashcalc
- Rainbow Crack

## Resources

- **Damn Vulnerable Web Application (DVWA)**
  - DVWA is a PHP/MYSQL vulnerable website that's made to be easy to hack. It's used to practice common web problems. It has different levels of difficulty. DVWA is important for the CEH (Practical) exam. It's a good idea to practice on DVWA because the exam might have similar challenges.
  - You can refer to the [DVWA Ultimate Guide](https://bughacking.com/dvwa-ultimate-guide-first-steps-and-walkthrough/) for a full guide on the setup and use of DVWA.

- **Hack The Box**
  - Challenges Steganography and Web: [Hack The Box](https://www.hackthebox.eu/)

- **Vulnhub**
  - Machines Easy to Medium: [Vulnhub](https://www.vulnhub.com/)

- **TryHackMe**
  - I enjoyed this platform a lot! It is an online platform for learning cybersecurity using hands-on exercises and labs. You can use a free version, but you can even use a paid one for a better experience.
  - There are many rooms but below I listed the ones I think are helpful for the exam along with the topics:
    - [Linux Fundamentals](https://tryhackme.com/module/linux-fundamentals)
    - [Hashing Crypto 101](https://tryhackme.com/room/hashingcrypto101)
    - [Crack The Hash](https://tryhackme.com/room/crackthehash)
    - [John The Ripper](https://tryhackme.com/room/johntheripper0)
    - [Hydra](https://tryhackme.com/room/hydra)
    - [Burp Suite](https://tryhackme.com/room/rpburpsuite)
    - [Network Services](https://tryhackme.com/room/networkservices)
    - [Metasploit](https://tryhackme.com/room/rpmetasploit)
    - [Further Nmap](https://tryhackme.com/room/furthernmap)
    - [Wireshark](https://tryhackme.com/room/wireshark)
    - [SQL Injection Basics](https://tryhackme.com/room/sqlibasics)
    - [OWASP Top 10](https://tryhackme.com/room/owasptop10) (recommended)
    - [Advent of Cyber 3](https://tryhackme.com/room/adventofcyber3) (recommended)
    - [CCPentesting](https://tryhackme.com/room/ccpentesting) (recommended)
    - [ZTH Web](https://tryhackme.com/room/zthweb2)
    - CTFs that combine all the knowledge you got from other rooms:
      - [Picklerick](https://tryhackme.com/room/picklerick)
      - [OWASP Juice Shop](https://tryhackme.com/room/owaspjuiceshop)
      - [Brooklyn Nine Nine](https://tryhackme.com/room/brooklynninenine)
      - [Lianyu](https://tryhackme.com/room/lianyu)
      - [Anthem](https://tryhackme.com/room/anthem)
      - [Agent Sudo CTF](https://tryhackme.com/room/agentsudoctf)
      - [Easy CTF](https://tryhackme.com/room/easyctf)
      - [AttackerKB](https://tryhackme.com/room/attackerkb)
      - [Kenobi](https://tryhackme.com/room/kenobi)
      - [Avengers](https://tryhackme.com/room/avengers)
      - [Tools R Us](https://tryhackme.com/room/toolsrus)
      - [Jurassic Park](https://tryhackme.com/room/jurassicpark)
      - [Blue](https://tryhackme.com/room/blue)

## All the commands that you need to know

- How many machines are active in a network: `net discover -i 192.168.1.0/24`
- Connect to RDP via cmd: `mstsc`
- Find DNS records: [nslookup.io](https://www.nslookup.io/)
- Scan the whole website: `skipfish -o /root/test -S /usr/share/skipfish/dictionaries/complete.wl http://10.10.10.10:8080`
  - `-o output`
  - `-S wordlist`
- To brute force directories or files:
  - `robuster dir -u 10.10.10.10 -w /usr/share/dirb/wordlists/common.txt -x .txt`
  - OR
  - `uniscan -u http://10.10.10.12:8080/CEH -q` (for directories)
  - `uniscan –u http://10.10.10.12:8080/CEH -we` (enable file check like robots.txt and sitemap.xml)
- To get the file from the server: `get http://10.10.10.10/secret.txt`
- FTP Login: `ftp <ip>`
  - `get <file name>` (to get file from FTP login)
- SSH Login: `SSH username@10.10.10.10`
- Nmap scan:
  - `Nmap -A 10.10.10.10` (aggressive scan- Traceroute, T4, OS)
  - `nmap -sC` (service scan)
  - `nmap -sV` (version scan)
  - `nmap -sP 10.10.10.10/24` (how many hosts are up in the whole network/ping scan)
  - `nmap -sL` (hostnames)
  - `nmap -oN <filename>` (to save output in a file)
  - `nmap -F` (fast scan)
  - `nmap -O` (OS scan)
- Crack the hashes:
  - `hashid -m <hash>` (to identify the type of hash, its mode, etc.)
  - `hashcat -m <mode> -a 0 <hashhhhhhhh> /usr/share/wordlist/rockyou.txt`
  - `crackstation`
  - `hashes.com`
  - `Cyberchef`
- Enumeration:
  - Global network inventory
  - Netbios enumerator
  - Hyena
  - Superscan
  - Advanced IP scanner
  - Nmap SMB scripts:
    - `nmap --script smb-os-discovery.nse -p445 <ip>` (enumerate OS, domain name, etc.)
    - `nmap --script smb-enum-users.nse -p445 <ip>` (enumerate all users on remote Windows system using SAMR enumeration and LSA bruteforcing)
    - `nmap -p 445 --script=smb-enum-shares.nse, smb-enum-users.nse 10.10.19.21` (SMB users and shares)
    - `smbclient //10.10.19.21/anonymous` (accessing SMB shares)
    - `smbget -R smb://10.10.19.21/anonymous` (downloading SMB files)
  - `enum4linux`
    - `enum4linux -u martin -p apple -U 10.10.10.12 | - u user -p pass -U get user list`
    - `enum4linux -u martin -p apple -o 10.10.10.12 | -o get OS info`
    - `enum4linux -u martin -p apple -P 10.10.10.12 | -P get password policy info`
    - `enum4linux -u martin -p apple -G 10.10.10.12 | -G get groups and members info`
    - `enum4linux -u martin -p apple -S 10.10.10.12 | -S get share list info`
    - `enum4linux -u martin -p apple -a 10.10.10.12 | -a get all simple enumeration data [-U -S -G -P -r -o -n -i]`
- Wpscan:
  - `wpscan --url http://[IP Address]:8080/CEH --enumerate u` (enumerate the usernames stored in the website’s database)
- Vulnerability analysis:
  - `nikto -h http://testphp.vulnweb.com/login.php -Tuning 1`
- Bruteforce:
  - `Hydra -L username -P /usr/share/wordlists/rockyou.txt ftp://xiotz.com`
- Cryptography:
  - Hashcalc
  - Md5 calculator
  - Cryptool – decode .hex file
  - Bctextencoder – decrypt text using secret key
  - Veracrypt – anything related to volume
  - Crack hashes- hashes.com, cyberchef
- Steganography:
  - `Steghide embed -ef <filename> -cf <image> -p <passphrase>`
  - `Steghide extract -sf <image>` (extract hidden data from image)
  - `Stegcracker <image> /usr/share/wordlists/rockyou.txt` (crack the passphrase of image)
  - [Online Steganography Tool](https://futureboy.us/stegano/decinput.html)
  - `sha256sum <filename>` (find hash of the file)
- Android Hacking:
  - via USB
    - `./adb tcpip 5555`
    - `./adb connect 192.168.43.117:5555`
    - `./adb devices`
    - `./adb -d shell` (Direct an adb command to the only attached USB device)
    - `ls`
    - `cd sdcard`
    - `ls`
    - `cd dcim`
    - `cd camera`
    - `ls`
    - `./adb push C:\platform-tools\ota.zip /sdcard/Download` (from PC to Android)
    - `./adb pull /sdcard/Download/magisk_patched.img C:\platform-tools` (from Android to PC)
  - `sqlmap`
    - `site:http://testphp.vulnweb.com/ php?=` (for finding vulnerable site)
    - (for cookies- console->document.cookie)
    - `sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 --dbs` (databases)
    - `sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart –tables` (tables)
    - `sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart -T users --columns` (columns)
    - (dump whole table)
    - `sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart -T users --dump`
    - OR (dump individual column data)
    - `sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart -T users -C uname --dump`
    - `sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart -T users -C pass --dump`

Thank you for reading this blog. I hope this blog finds you helpful. Visit our other blogs to know more about cybersecurity and the future of cybersecurity and how you can make your career in cybersecurity.
