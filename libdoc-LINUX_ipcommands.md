---
title: LINUX_ipcommands
description: LINUX_ipcommands
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 210
#unlisted: true
---
* 
{:toc}

- `ip [OPTION] OBJECT {COMMAND | help}`

- **Objects (or subcommands) you will use most often include:**
  1. `link` (`l`) – Used to display and modify network interfaces.
  2. `address` (`addr/a`) – Used to display and modify protocol addresses (IP, IPv6).
  3. `route` (`r`) – Used to display and alter the routing table.
  4. `neigh` (`n`) – Used to display and manipulate neighbor objects (ARP table).

- There are many other objects and commands available. To see a full list, type:



- To execute commands, you can use either full or abbreviated forms. For example, `ip link` and `ip l` will give the same results.

- **When configuring network interfaces:** 
- You must run the commands as root or a user with sudo privileges.
- By default, the system does not retain changes permanently after a restart.

- **Two ways to make adjustments permanent:**
1. Add commands to a startup script.
2. Edit distro-specific configuration files.

- **Manage and Display Network Interfaces:**
- Get a list of all `link` command options and more by typing:
  ```
  ip link help
  ```

- **Get Network Interface Information:**
  - To see link-layer information of all available devices:
    ```
    ip link show
    ```
  - To display information about a specific device:
    ```
    ip link show dev [device]
    ```

- To see statistics for all network interfaces:
  ```
  ip -s link
  ```

- To see similar information for an individual network interface:
  ```
  ip -s link ls [interface]
  ```

- To see a list of only the running interfaces:
  ```
  ip link ls up
  ```

- **Modify Network Interface Status:**
  - Bring a network interface up (online):
    ```
    ip link set [interface] up
    ```
  - Disable an interface (offline):
    ```
    ip link set [interface] down
    ```

  - Modify the transmit queue:
    ```
    ip link set txqueuelen [number] dev [interface]
    ```

  - Set the MTU (Maximum Transmission Unit):
    ```
    ip link set mtu [number] dev [interface]
    ```

- Find all the `link` command options:
  ```
  ip link help
  ```

- **Monitor and Manage IP Addresses:**
  - Check all `address` commands and more:
    ```
    ip addr help
    ```

  - **Monitor IP Addresses:**
    - Display all devices:
      ```
      ip addr
      ```

    - List all network interfaces and associated IP addresses:
      ```
      ip addr show
      ```

    - See information about an individual network:
      ```
      ip addr show dev [interface]
      ```

    - List IPv4 addresses:
      ```
      ip -4 addr
      ```

    - List IPv6 addresses:
      ```
      ip -6 addr
      ```

- **How to Add IP Address in Linux:**
  - Add an IP address to an interface:
    ```
    ip addr add [ip_address] dev [interface]
    ```

  - Add a broadcast address to an interface:
    ```
    ip addr add brd [ip_address] dev [interface]
    ```

  - Remove an IP address from an interface:
    ```
    ip addr del [ip_address] dev [interface]
    ```

- **Manage and Display IP Routing Table:**
  - See a full list of `ip route` commands:
    ```
    ip route help
    ```

  - **Display IP Routing Table:**
    - List all route entries:
      ```
      ip route 
      ```

    - List all route entries (alternative command):
      ```
      ip route list
      ```

    - Narrow down the search with a SELECTOR object:
      ```
      ip route list SELECTOR
      ```

    - View routing for a distinct network:
      ```
      ip route list [ip_address]
      ```

  - **Modify IP Routing Table:**
    - Add a new entry in the routing table:
      ```
      ip route add [ip_address] dev [interface]
      ```

    - Add a new route via gateway:
      ```
      ip route add [ip_address] via [gatewayIP]
      ```

    - Add a route for all addresses via the local gateway:
      ```
      ip route add default [ip_address] dev [device]
      ```
      ```
      ip route add default [network/mask] via [gatewayIP]
      ```

    - Delete an existing entry in the routing table:
      ```
      ip route del [ip_address]
      ```
      ```
      ip route del default
      ```
      ```
      ip route del [ip_address] dev [interface]
      ```

- **Display and Modify IP Neighbor Entries:**
  - See a full list of `ip neigh` command options:
    ```
    ip neigh help
    ```

  - **Display IP Neighbor Entries:**
    - Display neighbor tables:
      ```
      ip neigh show
      ```

  - **Modify IP Neighbor Entries:**
    - Add a new table entry:
      ```
      ip neigh add [ip_address] dev [interface]
      ```

    - Remove an existing ARP entry:
      ```
      ip neigh del [ip_address] dev [interface]
      ```

- **Conclusion:**
- You now know what the `ip` command in Linux is and how to use it for network/system administration.

- **Next Steps:**
- Discover more Linux Commands in our Cheat Sheet and Tutorial With Examples.
