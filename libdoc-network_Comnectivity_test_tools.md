---
title: network_Comnectivity_testtools
description: network_Comnectivity_testtools
layout: libdoc/page

#LibDoc specific below
category: Troubleshooting
order: 90
#unlisted: true
---
* 
{:toc}


## Troubleshooting Commands for Windows Network Connectivity, Latency, and Bandwidth

| Command               | Description                                                            | Example                                 |
|-----------------------|------------------------------------------------------------------------|-----------------------------------------|
| [`ping` ](#ping)               | Tests connectivity to a specified host and measures round-trip time.   | `ping google.com`                       |
| [`tracert`](#tracert)             | Traces the path packets take to a network host.                        | `tracert google.com`                    |
| [`ipconfig` ](#ipconfig)           | Displays IP configuration information for all network adapters.        | `ipconfig /all`                         |
| [`ipconfig /release`](#description-6)   | Releases the current DHCP-assigned IP address.                         | `ipconfig /release`                     |
| `ipconfig /renew`     | Renews the DHCP-assigned IP address.                                   | `ipconfig /renew`                       |
| [`nslookup` ](#nslookup)           | Queries DNS servers for domain name or IP address information.         | `nslookup google.com`                   |
| [`netstat` ](#netstat)            | Displays active connections and listening ports.                       | `netstat -an`                           |
| [`netsh`](#netsh)               | Configures network settings and diagnostics.                           | `netsh int ip reset`                    |
| [`pathping`](#pathping)            | Combines `ping` and `tracert` for detailed analysis of packet loss.    | `pathping google.com`                   |
| [`getmac`](#getmac)              | Displays the MAC addresses of network adapters.                        | `getmac`                                |
| [`route`](#route)               | Displays and modifies the IP routing table.                            | `route print`                           |
| `arp`                 | Displays and modifies the ARP cache.                                   | `arp -a`                                |
| `tasklist`            | Lists all running processes (useful for identifying network-intensive apps). | `tasklist`                              |
| `netsh wlan show all` | Displays detailed information about all available wireless networks.   | `netsh wlan show all`                   |
| `netsh interface ipv4 show subinterfaces` | Displays information about subinterfaces.         | `netsh interface ipv4 show subinterfaces` |
| `powercfg`            | Configures power settings (useful for ensuring network adapters aren't being powered down). | `powercfg -a`                |
| `netsh advfirewall`   | Configures and manages Windows Firewall settings.                      | `netsh advfirewall show allprofiles`    |
| `ping -t`             | Continuously pings a specified host until stopped.                     | `ping -t google.com`                    |
| `netsh int tcp set global autotuninglevel=disabled` | Disables TCP auto-tuning to troubleshoot network performance issues. | `netsh int tcp set global autotuninglevel=disabled` |
| `perfmon`             | Opens the Performance Monitor for real-time system performance tracking. | `perfmon`                              |
| `wireshark`           | Captures and analyzes network packets (third-party tool).              | `wireshark`                             |
| `tcping`              | Tests TCP connectivity to a specified port (third-party tool).         | `tcping google.com 80`                  |

# [` Step-by-Step Troubleshooting Guide `](#step-by-step-troubleshooting-guide-1)

This table provides a variety of commands to diagnose and troubleshoot network connectivity, latency, and bandwidth issues on Windows systems. Let me know if you need further details or examples for any specific command.

Certainly! Below is a detailed breakdown of each command, including their options and usage scenarios, formatted in Markdown:


## Detailed Usage of Windows Network Troubleshooting Commands

### `ping`

#### Description
Tests connectivity to a specified host and measures round-trip time.

#### Options
| Option   | Description                          | Example                   |
|----------|--------------------------------------|---------------------------|
| `-t`     | Ping the specified host until stopped. | `ping -t google.com`      |
| `-n`     | Number of echo requests to send.     | `ping -n 10 google.com`   |
| `-l`     | Send buffer size.                    | `ping -l 1024 google.com` |
| `-4`     | Force using IPv4.                    | `ping -4 google.com`      |
| `-6`     | Force using IPv6.                    | `ping -6 google.com`      |

#### Usage Scenario
To continuously ping Google's server until you manually stop it:
```sh
ping -t google.com
```

### `tracert`

#### Description
Traces the path packets take to a network host.

#### Options
| Option   | Description                                | Example                     |
|----------|--------------------------------------------|-----------------------------|
| `-d`     | Do not resolve addresses to hostnames.     | `tracert -d google.com`     |
| `-h`     | Maximum number of hops to search for target. | `tracert -h 15 google.com`  |
| `-4`     | Force using IPv4.                          | `tracert -4 google.com`     |
| `-6`     | Force using IPv6.                          | `tracert -6 google.com`     |

#### Usage Scenario
To trace the route to Google's server without resolving IP addresses to hostnames:
```sh
tracert -d google.com
```

### `ipconfig`

#### Description
Displays IP configuration information for all network adapters.

#### Options
| Option        | Description                              | Example                     |
|---------------|------------------------------------------|-----------------------------|
| `/all`        | Display full configuration information.  | `ipconfig /all`             |
| `/release`    | Release the current DHCP-assigned IP address. | `ipconfig /release`        |
| `/renew`      | Renew the DHCP-assigned IP address.      | `ipconfig /renew`           |
| `/flushdns`   | Purge the DNS Resolver cache.            | `ipconfig /flushdns`        |
| `/displaydns` | Display the contents of the DNS Resolver cache. | `ipconfig /displaydns` |

#### Usage Scenario
To view detailed IP configuration information:
```sh
ipconfig /all
```

### `nslookup`

#### Description
Queries DNS servers for domain name or IP address information.

#### Options
| Option        | Description                                | Example                         |
|---------------|--------------------------------------------|---------------------------------|
| `-type=type`  | Specify the query type (e.g., A, MX, NS).  | `nslookup -type=MX google.com`  |
| `server`      | Specify the DNS server to use for the query. | `nslookup google.com 8.8.8.8`   |

#### Usage Scenario
To query the DNS records of Google's mail servers:
```sh
nslookup -type=MX google.com
```

### `netstat`

#### Description
Displays active connections and listening ports.

#### Options
| Option   | Description                                 | Example                 |
|----------|---------------------------------------------|-------------------------|
| `-a`     | Displays all connections and listening ports. | `netstat -a`            |
| `-n`     | Displays addresses and port numbers in numerical form. | `netstat -n`    |
| `-o`     | Displays the owning process ID associated with each connection. | `netstat -o` |
| `-e`     | Displays Ethernet statistics.               | `netstat -e`            |
| `-p proto` | Shows connections for the specified protocol (TCP/UDP). | `netstat -p tcp` |

#### Usage Scenario
To view all active connections and listening ports:
```sh
netstat -an
```

### `netsh`

#### Description
Configures network settings and diagnostics.

#### Options
| Option          | Description                                          | Example                       |
|-----------------|------------------------------------------------------|-------------------------------|
| `int ip reset`  | Resets TCP/IP settings to default.                   | `netsh int ip reset`          |
| `advfirewall show allprofiles` | Displays current Windows Firewall settings. | `netsh advfirewall show allprofiles` |

#### Usage Scenario
To reset TCP/IP settings to default:
```sh
netsh int ip reset
```

### `pathping`

#### Description
Combines `ping` and `tracert` for detailed analysis of packet loss.

#### Options
| Option   | Description                                    | Example                |
|----------|------------------------------------------------|------------------------|
| `-n`     | Do not resolve addresses to hostnames.         | `pathping -n google.com` |
| `-h`     | Maximum number of hops to search for target.   | `pathping -h 15 google.com` |

#### Usage Scenario
To analyze the route to Google's server with packet loss information:
```sh
pathping google.com
```

### `getmac`

#### Description
Displays the MAC addresses of network adapters.

#### Options
| Option   | Description                                    | Example                |
|----------|------------------------------------------------|------------------------|
| `/v`     | Display verbose output.                        | `getmac /v`            |
| `/fo`    | Specifies the format of the output (TABLE, LIST, CSV). | `getmac /fo csv` |

#### Usage Scenario
To display MAC addresses in verbose format:
```sh
getmac /v
```

### `route`

#### Description
Displays and modifies the IP routing table.

#### Options
| Option        | Description                                    | Example                  |
|---------------|------------------------------------------------|--------------------------|
| `print`       | Displays the current routing table.            | `route print`            |
| `add`         | Adds a route to the routing table.             | `route add 192.168.1.0 MASK 255.255.255.0 192.168.0.1` |
| `delete`      | Deletes a route from the routing table.        | `route delete 192.168.1.0` |
| `change`      | Modifies an existing route.                    | `route change 192.168.1.0 MASK 255.255.255.0 192.168.0.2` |

#### Usage Scenario
To add a route to the routing table:
```sh
route add 192.168.1.0 MASK 255.255.255.0 192.168.0.1
```

### `arp`

#### Description
Displays and modifies the ARP cache.

#### Options
| Option   | Description                                    | Example               |
|----------|------------------------------------------------|-----------------------|
| `-a`     | Displays current ARP entries.                  | `arp -a`              |
| `-d`     | Deletes an ARP entry.                          | `arp -d 192.168.0.1`  |
| `-s`     | Adds a static ARP entry.                       | `arp -s 192.168.0.1 00-AA-BB-CC-DD-EE` |

#### Usage Scenario
To display the current ARP entries:
```sh
arp -a
```

### `tasklist`

#### Description
Lists all running processes (useful for identifying network-intensive apps).

#### Options
| Option        | Description                                    | Example               |
|---------------|------------------------------------------------|-----------------------|
| `/svc`        | Shows services hosted in each process.         | `tasklist /svc`       |
| `/v`          | Displays verbose output.                       | `tasklist /v`         |
| `/fi`         | Displays a set of tasks that match a given criteria. | `tasklist /fi "USERNAME ne SYSTEM"` |

#### Usage Scenario
To display all running processes in verbose format:
```sh
tasklist /v
```

### `netsh wlan show all`

#### Description
Displays detailed information about all available wireless networks.

#### Options
| Option   | Description                                    | Example               |
|----------|------------------------------------------------|-----------------------|
| `show all` | Displays detailed information about all wireless networks. | `netsh wlan show all` |

#### Usage Scenario
To display detailed information about all available wireless networks:
```sh
netsh wlan show all
```

### `netsh interface ipv4 show subinterfaces`

#### Description
Displays information about subinterfaces.

#### Options
| Option   | Description                                    | Example               |
|----------|------------------------------------------------|-----------------------|
| `show subinterfaces` | Displays information about subinterfaces. | `netsh interface ipv4 show subinterfaces` |

#### Usage Scenario
To display information about subinterfaces:
```sh
netsh interface ipv4 show subinterfaces
```

### `powercfg`

#### Description
Configures power settings (useful for ensuring network adapters aren't being powered down).

#### Options
| Option        | Description                                    | Example                |
|---------------|------------------------------------------------|------------------------|
| `-a`          | Displays the available sleep states of the system. | `powercfg -a`         |
| `-h on/off`   | Enables/disables hibernation.                  | `powercfg -h off`      |
| `-energy`     | Analyzes

 the system for common energy efficiency and battery life problems. | `powercfg -energy` |

#### Usage Scenario
To display the available sleep states of the system:
```sh
powercfg -a
```

### `netsh advfirewall`

#### Description
Configures and manages Windows Firewall settings.

#### Options
| Option                       | Description                                    | Example                                  |
|------------------------------|------------------------------------------------|------------------------------------------|
| `show allprofiles`           | Displays current Windows Firewall settings for all profiles. | `netsh advfirewall show allprofiles` |
| `set allprofiles state off`  | Disables Windows Firewall for all profiles.    | `netsh advfirewall set allprofiles state off` |

#### Usage Scenario
To display current Windows Firewall settings for all profiles:
```sh
netsh advfirewall show allprofiles
```

### `tcping`

#### Description
Tests TCP connectivity to a specified port (third-party tool).

#### Options
| Option        | Description                                    | Example                   |
|---------------|------------------------------------------------|---------------------------|
| `-t`          | Ping the specified host until stopped.         | `tcping -t google.com 80` |
| `-n`          | Number of echo requests to send.               | `tcping -n 10 google.com 80` |
| `-i`          | Interval between pings in seconds.             | `tcping -i 2 google.com 80` |

#### Usage Scenario
To test TCP connectivity to Google's server on port 80:
```sh
tcping google.com 80
```

### `wireshark`

#### Description
Captures and analyzes network packets (third-party tool).

#### Options
Wireshark has a graphical user interface, so commands are used within the GUI. Commonly used filters include:

| Filter        | Description                                    | Example                        |
|---------------|------------------------------------------------|--------------------------------|
| `ip.addr==x.x.x.x` | Displays packets to or from a specific IP address. | `ip.addr==192.168.0.1`         |
| `tcp.port==x` | Displays packets with a specific TCP port.     | `tcp.port==80`                 |
| `udp.port==x` | Displays packets with a specific UDP port.     | `udp.port==53`                 |

#### Usage Scenario
To capture and analyze network packets:
1. Open Wireshark.
2. Select the network interface.
3. Use the filter to display packets to or from a specific IP address:
```sh
ip.addr==192.168.0.1
```

This detailed breakdown should help in using each command effectively for troubleshooting network issues on Windows systems. Let me know if you need further details or additional commands.

Troubleshooting latency and connectivity issues involves several steps and commands to identify the root cause and then implement fixes. Below is a structured approach to troubleshoot and fix these issues:

# Step-by-Step Troubleshooting Guide

#### 1. Verify Physical Connections
- **Check all cables and connections.**
- Ensure that the network devices (routers, switches, etc.) are powered on.

#### 2. Check IP Configuration
- Use `ipconfig` to verify the IP configuration.
  ```sh
  ipconfig /all
  ```
- Ensure that the IP address, subnet mask, gateway, and DNS servers are correctly configured.

#### 3. Test Basic Connectivity
- Use `ping` to test connectivity to the default gateway and an external server.
  ```sh
  ping 192.168.1.1        # Gateway
  ping google.com         # External server
  ```
- If `ping` to the gateway fails, there might be an issue with your local network.
- If `ping` to the external server fails, the issue might be with the ISP or beyond.

#### 4. Trace the Route
- Use `tracert` to trace the path to an external server.
  ```sh
  tracert google.com
  ```
- Identify any points in the route where latency spikes or where the trace fails.

#### 5. Check for Packet Loss
- Use `pathping` to combine the functionality of `ping` and `tracert` and check for packet loss.
  ```sh
  pathping google.com
  ```

#### 6. DNS Issues
- Use `nslookup` to verify DNS resolution.
  ```sh
  nslookup google.com
  ```
- If DNS resolution fails, try changing the DNS server to a public DNS (e.g., Google's 8.8.8.8).

#### 7. Check Network Utilization
- Use `netstat` to check for excessive network connections or suspicious activity.
  ```sh
  netstat -an
  ```
- Identify any unusual connections or a large number of connections.

#### 8. Analyze Wireless Networks (if applicable)
- Use `netsh wlan show all` to display detailed information about wireless networks.
  ```sh
  netsh wlan show all
  ```
- Check for interference, weak signals, or too many devices on the same channel.

#### 9. Update Network Drivers
- Ensure that the network adapter drivers are up to date. Check the manufacturer's website for the latest drivers.

#### 10. Check for Malware
- Run a full system antivirus scan to check for malware that might be causing network issues.

### Fixing Common Issues

#### Fix IP Configuration Issues
- If the IP configuration is incorrect, release and renew the IP address.
  ```sh
  ipconfig /release
  ipconfig /renew
  ```

#### Fix DNS Issues
- Change the DNS server to a public DNS server like Google's.
  ```sh
  netsh interface ipv4 set dns "Local Area Connection" static 8.8.8.8
  ```

#### Reset TCP/IP Stack
- Reset the TCP/IP stack to fix potential configuration issues.
  ```sh
  netsh int ip reset
  ```

#### Disable Auto-Tuning
- Disable TCP auto-tuning if experiencing network performance issues.
  ```sh
  netsh int tcp set global autotuninglevel=disabled
  ```

#### Adjust Router Settings
- Ensure the router firmware is up to date.
- Change the wireless channel to a less congested one.

#### Optimize Network Adapter Settings
- Disable power-saving settings for network adapters to prevent them from being powered down.
  ```sh
  powercfg -h off
  ```

### Usage Scenarios and Commands

#### Scenario 1: Slow Internet Connection
1. **Check Physical Connections:**
   - Ensure all cables are properly connected.
2. **Verify IP Configuration:**
   - ```sh
     ipconfig /all
     ```
3. **Test Connectivity:**
   - ```sh
     ping google.com
     ```
4. **Trace Route:**
   - ```sh
     tracert google.com
     ```
5. **Check for Packet Loss:**
   - ```sh
     pathping google.com
     ```
6. **Change DNS Server:**
   - ```sh
     netsh interface ipv4 set dns "Local Area Connection" static 8.8.8.8
     ```
7. **Reset TCP/IP Stack:**
   - ```sh
     netsh int ip reset
     ```

#### Scenario 2: Intermittent Connectivity Issues
1. **Check Wireless Network Information:**
   - ```sh
     netsh wlan show all
     ```
2. **Test Connectivity:**
   - ```sh
     ping google.com
     ```
3. **Check for Packet Loss:**
   - ```sh
     pathping google.com
     ```
4. **Update Network Drivers:**
   - Download and install the latest drivers from the manufacturer’s website.
5. **Run Antivirus Scan:**
   - Run a full system scan using your antivirus software.

By following these steps and using the provided commands, you can systematically troubleshoot and fix network latency and connectivity issues on a Windows system.
