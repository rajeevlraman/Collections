---
title: netstat_commands
description: netstat_commands
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 214
#unlisted: true
---
* 
{:toc}


# Comprehensive Netstat Commands

## Basic Netstat Commands

| **Command**                     | **Description**                                | **Example**                           |
|---------------------------------|------------------------------------------------|---------------------------------------|
| `netstat -a`                    | Display all active connections and listening ports | `netstat -a`                        |
| `netstat -t`                    | Display only TCP connections                   | `netstat -t`                         |
| `netstat -u`                    | Display only UDP connections                   | `netstat -u`                         |
| `netstat -l`                    | Show only listening ports                      | `netstat -l`                         |
| `netstat -p`                    | Show connections and the process that owns them | `netstat -p`                        |
| `netstat -s`                    | Display summary statistics for each protocol   | `netstat -s`                         |
| `netstat -r`                    | Display the routing table                      | `netstat -r`                         |
| `netstat -i`                    | Display network interfaces and their statistics | `netstat -i`                        |
| `netstat -e`                    | Display Ethernet statistics                    | `netstat -e`                         |
| `netstat -n`                    | Show numerical addresses instead of resolving hosts | `netstat -n`                  |
| `netstat -c`                    | Continuously display network status            | `netstat -c`                         |
| `netstat --tcp`                 | Display only TCP protocol                      | `netstat --tcp`                      |
| `netstat --udp`                 | Display only UDP protocol                      | `netstat --udp`                      |

## Filtering and Display Options

| **Command**                      | **Description**                                            | **Example**                           |
|----------------------------------|------------------------------------------------------------|---------------------------------------|
| `netstat -an`                    | Display all connections and listening ports in numeric form | `netstat -an`                         |
| `netstat -at`                    | Show only TCP connections in numeric form                  | `netstat -at`                         |
| `netstat -au`                    | Show only UDP connections in numeric form                  | `netstat -au`                         |
| `netstat -lt`                    | List only listening TCP ports                              | `netstat -lt`                         |
| `netstat -lu`                    | List only listening UDP ports                              | `netstat -lu`                         |
| `netstat -lx`                    | List only listening UNIX domain sockets                    | `netstat -lx`                         |
| `netstat -tp`                    | Display TCP connections and the PID/Program name           | `netstat -tp`                         |
| `netstat -up`                    | Display UDP connections and the PID/Program name           | `netstat -up`                         |
| `netstat -lp`                    | Show only listening ports with PID/Program name            | `netstat -lp`                         |

## Advanced Options

| **Command**                      | **Description**                                            | **Example**                           |
|----------------------------------|------------------------------------------------------------|---------------------------------------|
| `netstat -g`                     | Display multicast group memberships                        | `netstat -g`                          |
| `netstat -M`                     | Display masqueraded connections                            | `netstat -M`                          |
| `netstat -v`                     | Verbose mode, providing additional details                 | `netstat -v`                          |
| `netstat -W`                     | Do not truncate IP addresses                               | `netstat -W`                          |
| `netstat -B`                     | Show the socket buffers                                    | `netstat -B`                          |
| `netstat -C`                     | Show routing cache information                             | `netstat -C`                          |
| `netstat -Z`                     | Zero the statistics                                        | `netstat -Z`                          |

## Combining Options

| **Command**                      | **Description**                                            | **Example**                           |
|----------------------------------|------------------------------------------------------------|---------------------------------------|
| `netstat -ltn`                   | List all listening TCP ports in numeric form               | `netstat -ltn`                        |
| `netstat -lpu`                   | List all listening UDP ports with PID/Program name         | `netstat -lpu`                        |
| `netstat -tuln`                  | List all listening TCP and UDP ports in numeric form       | `netstat -tuln`                       |
| `netstat -tunap`                 | Display all TCP and UDP connections with PID/Program name  | `netstat -tunap`                      |
| `netstat -s -p tcp`              | Display detailed TCP protocol statistics                   | `netstat -s -p tcp`                   |
| `netstat -s -p udp`              | Display detailed UDP protocol statistics                   | `netstat -s -p udp`                   |
| `netstat -g -p`                  | Display multicast group memberships with PID/Program name  | `netstat -g -p`                       |

## Platform-Specific Commands (Windows)

| **Command**                      | **Description**                                            | **Example**                           |
|----------------------------------|------------------------------------------------------------|---------------------------------------|
| `netstat -b`                     | Show executable involved in creating each connection       | `netstat -b`                          |
| `netstat -o`                     | Display the owning process ID associated with each connection | `netstat -o`                       |
| `netstat -e`                     | Display Ethernet statistics (sent and received bytes)      | `netstat -e`                          |
| `netstat -f`                     | Display fully qualified domain names for foreign addresses | `netstat -f`                          |
| `netstat -x`                     | Display NetworkDirect connections, listeners, and shared endpoints | `netstat -x`                   |
| `netstat -y`                     | Display the TCP connection template for all connections    | `netstat -y`                          |
| `netstat -b -o -n`               | Display connections with executable, PID, and numerical addresses | `netstat -b -o -n`             |

## Display Help

| **Command**                      | **Description**                                            | **Example**                           |
|----------------------------------|------------------------------------------------------------|---------------------------------------|
| `netstat -h`                     | Show netstat help menu                                     | `netstat -h`                          |
| `netstat --help`                 | Display extended help information                          | `netstat --help`                      |

```

This table includes a wide range of `netstat` options and combinations, providing detailed descriptions and examples for each command. Feel free to refer back to this anytime you need a quick reference for `netstat` commands!
