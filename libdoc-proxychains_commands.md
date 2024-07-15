---
title: proxychains_commands
description: proxychains_commands
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 216
#unlisted: true
---
* 
{:toc}

`proxychains` is a tool that forces any TCP connection made by any given application to go through proxy servers like SOCKS4, SOCKS5, or HTTP(S). This is especially useful for anonymizing traffic or accessing services restricted by region.

Here’s how you can use `proxychains` with various commands and applications:

```markdown
## ProxyChains Commands
[Back to top](#categories)

### Basic Usage

- **Running a command through proxychains**:
  ```bash
  proxychains <command>
  ```
  Example:
  ```bash
  proxychains curl http://example.com
  proxychains wget http://example.com/file.zip
  ```

### Configuring ProxyChains

- **Edit the ProxyChains configuration file**:
  ```bash
  nano /etc/proxychains.conf
  ```
  This file allows you to set up your list of proxy servers and other configurations.

### Examples of ProxyChains Usage

- **Using `proxychains` with `curl`**:
  ```bash
  proxychains curl -I https://www.example.com
  ```

- **Using `proxychains` with `wget`**:
  ```bash
  proxychains wget https://www.example.com/file.zip
  ```

- **Using `proxychains` with `ssh`**:
  ```bash
  proxychains ssh user@hostname
  ```

- **Using `proxychains` with `git`**:
  ```bash
  proxychains git clone https://github.com/username/repository.git
  ```

- **Using `proxychains` with `apt-get`**:
  ```bash
  proxychains sudo apt-get update
  proxychains sudo apt-get install package
  ```

### ProxyChains Configuration Options

- **Dynamic chain**: This option allows `proxychains` to use any available proxy in the list in a random order.
  ```bash
  nano /etc/proxychains.conf
  ```
  Set `dynamic_chain` and comment out `strict_chain`:
  ```plaintext
  dynamic_chain
  # strict_chain
  ```

- **Strict chain**: Forces `proxychains` to use all the proxies in the list sequentially.
  ```bash
  nano /etc/proxychains.conf
  ```
  Set `strict_chain` and comment out `dynamic_chain`:
  ```plaintext
  # dynamic_chain
  strict_chain
  ```

- **Proxy list format in `/etc/proxychains.conf`**:
  ```plaintext
  [ProxyList]
  # add proxy here ...
  # meanwile
  # defaults set to "tor"
  socks4  127.0.0.1 9050
  socks5  127.0.0.1 1080
  http    127.0.0.1 8080
  ```
  Each line in the `[ProxyList]` section specifies a proxy server type, address, and port.

### Advanced Options

- **Using a custom configuration file**:
  ```bash
  proxychains -f /path/to/custom_proxychains.conf <command>
  ```
  Example:
  ```bash
  proxychains -f ~/.proxychains/proxychains.conf curl http://example.com
  ```

- **Quiet mode**: Suppress `proxychains` output.
  ```bash
  proxychains -q <command>
  ```
  Example:
  ```bash
  proxychains -q curl http://example.com
  ```

- **Debug mode**: Show detailed information about the proxies being used.
  ```bash
  proxychains -d <command>
  ```
  Example:
  ```bash
  proxychains -d wget http://example.com/file.zip
  ```

### Practical Use Cases

- **Bypassing IP restrictions**: Use `proxychains` to access services or websites that block IPs based on geolocation or other criteria.
  ```bash
  proxychains firefox
  ```

- **Enhancing security**: Route sensitive commands through multiple proxies for anonymity.
  ```bash
  proxychains ssh user@hostname
  ```

- **Automated scripts**: Include `proxychains` in scripts to ensure all outgoing traffic goes through proxies.
  ```bash
  #!/bin/bash
  proxychains curl -O http://example.com/file.zip
  ```

- **Testing network configurations**: Use `proxychains` to test how applications behave when accessed through different proxy servers.
  ```bash
  proxychains nmap -sT www.example.com
  ```

---

ProxyChains is a powerful tool for network traffic manipulation and provides flexibility in configuring and using various proxy types. Always ensure that your use of proxies complies with legal and ethical guidelines.
```
