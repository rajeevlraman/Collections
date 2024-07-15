---
title: AD_setup
description: AD_setup
layout: libdoc/page

#LibDoc specific below
category: Features
order: 96
#unlisted: true
---
*
{:toc}

---

## Active Directory (AD)

### Overview
Active Directory is a directory service developed by Microsoft for Windows domain networks. It stores information about objects on the network and makes this information easy for administrators and users to find and use. AD provides authentication and authorization services and enables centralized management of network resources.

### Setup

1. **Install Active Directory Domain Services (AD DS) Role:**
   - **Description**: AD DS is a server role that enables you to create and manage a domain, user accounts, and resources.
   - **Steps**:
     1. Open **Server Manager**.
     2. Click on **Add Roles and Features**.
     3. Select **Active Directory Domain Services**.
     4. Follow the wizard to install the role.
     5. After installation, promote the server to a domain controller by following the **Active Directory Domain Services Configuration Wizard**.

   - **Example**: Setting up AD DS to create a new domain "example.com".

2. **Create and Organize Organizational Units (OUs):**
   - **Description**: OUs help organize users, groups, and computers in a hierarchical structure within a domain.
   - **Steps**:
     1. Open **Active Directory Users and Computers**.
     2. Right-click on the domain, select **New** > **Organizational Unit**.
     3. Name the OU and define its purpose, e.g., "IT Department".

   - **Example**: Creating OUs for different departments like "HR", "IT", and "Finance".

3. **Manage User Accounts and Groups:**
   - **Description**: Add users and groups to the domain and assign them to appropriate OUs and groups.
   - **Steps**:
     1. Open **Active Directory Users and Computers**.
     2. Right-click on the appropriate OU, select **New** > **User**.
     3. Fill in user details and set up a password.
     4. Create groups and add users to groups as needed.

   - **Example**: Adding a new user "John Doe" to the "IT Department" OU and the "IT Support" group.

4. **Implement Group Policies:**
   - **Description**: Group Policies manage the working environment of user and computer accounts.
   - **Steps**:
     1. Open **Group Policy Management**.
     2. Right-click on the domain or OU, select **Create a GPO in this domain, and Link it here**.
     3. Configure the policy settings as required.

   - **Example**: Creating a policy to enforce password complexity requirements.

### Troubleshooting

1. **User Login Issues:**
   - **Problem**: A user cannot log in to the domain.
   - **Steps**:
     1. Verify the user’s credentials are correct.
     2. Check if the user account is disabled or locked out.
     3. Ensure the computer is connected to the domain.
     4. Verify DNS settings to ensure the computer can resolve the domain controller's address.
     5. Check the user’s profile in AD for any misconfigurations.

   - **Example**: A user cannot log in due to an expired password or incorrect DNS settings.

2. **Replication Problems:**
   - **Problem**: Changes made in one domain controller are not reflected on others.
   - **Steps**:
     1. Use **Repadmin** tools to check the replication status.
     2. Verify network connectivity between domain controllers.
     3. Check if the **NTDS Settings** are correctly configured.
     4. Ensure the **SYSVOL** folder is shared and accessible.

   - **Example**: Using `repadmin /showrepl` to identify replication failures.

3. **Group Policy Not Applying:**
   - **Problem**: Policies are not being enforced on users or computers.
   - **Steps**:
     1. Use **gpresult /r** to view the applied group policies on a system.
     2. Check the **Group Policy Management Console** for any issues in the policy configuration.
     3. Verify the policy scope and ensure it is linked to the correct OU or domain.
     4. Ensure there are no conflicting policies or higher precedence settings overriding it.

   - **Example**: A policy not applying because it's not linked to the correct OU.

---

## Domain Name System (DNS)

### Overview
DNS translates domain names to IP addresses, enabling computers to locate services and devices using human-readable names.

### Setup

1. **Install DNS Server Role:**
   - **Description**: DNS Server role manages the name resolution for your domain.
   - **Steps**:
     1. Open **Server Manager**.
     2. Click on **Add Roles and Features**.
     3. Select **DNS Server**.
     4. Follow the wizard to complete the installation.

   - **Example**: Installing the DNS role to manage the domain "example.com".

2. **Configure Forward Lookup Zones:**
   - **Description**: Forward Lookup Zones resolve domain names to IP addresses.
   - **Steps**:
     1. Open **DNS Manager**.
     2. Right-click on **Forward Lookup Zones**, select **New Zone**.
     3. Follow the wizard to create a new primary zone.
     4. Add A records to map domain names to IP addresses.

   - **Example**: Creating a zone for "example.com" and adding an A record for "www.example.com" pointing to IP address "192.168.1.10".

3. **Configure Reverse Lookup Zones:**
   - **Description**: Reverse Lookup Zones resolve IP addresses to domain names.
   - **Steps**:
     1. Open **DNS Manager**.
     2. Right-click on **Reverse Lookup Zones**, select **New Zone**.
     3. Follow the wizard to create a new primary zone.
     4. Add PTR records to map IP addresses to domain names.

   - **Example**: Creating a reverse zone for "192.168.1.x" and adding a PTR record for "192.168.1.10" pointing to "www.example.com".

4. **Configure DNS Forwarders:**
   - **Description**: Forwarders resolve DNS queries that your server cannot resolve.
   - **Steps**:
     1. Open **DNS Manager**.
     2. Right-click on the DNS server, select **Properties**.
     3. Go to the **Forwarders** tab and add the IP addresses of the external DNS servers.

   - **Example**: Adding Google DNS (8.8.8.8) as a forwarder.

### Troubleshooting

1. **DNS Resolution Issues:**
   - **Problem**: Clients cannot resolve domain names.
   - **Steps**:
     1. Verify that the DNS server is running and accessible.
     2. Check the DNS server settings and ensure forwarders are correctly configured.
     3. Use **nslookup** to query the DNS server and check for correct responses.
     4. Ensure that the necessary A and PTR records exist in the DNS zones.

   - **Example**: A client unable to resolve "www.example.com" because the A record is missing or incorrectly configured.

2. **Slow DNS Performance:**
   - **Problem**: DNS queries are slow to resolve.
   - **Steps**:
     1. Check for network latency or congestion affecting the DNS server.
     2. Verify the DNS server load and ensure it is not overwhelmed.
     3. Ensure that DNS caching is enabled and working properly.
     4. Optimize the DNS zone settings and clean up any stale or unnecessary records.

   - **Example**: Slow DNS queries due to excessive load or misconfigured caching.

3. **DNS Server Not Responding:**
   - **Problem**: DNS server is not responding to client queries.
   - **Steps**:
     1. Check if the DNS server service is running and restart it if necessary.
     2. Verify network connectivity between the DNS server and clients.
     3. Ensure that no firewall rules are blocking DNS traffic.
     4. Examine the server’s event logs for any DNS-related errors.

   - **Example**: DNS server not responding due to the service being stopped or network issues.

---

## Dynamic Host Configuration Protocol (DHCP)

### Overview
DHCP automates the assignment of IP addresses, subnet masks, gateways, and other IP parameters to network devices.

### Setup

1. **Install DHCP Server Role:**
   - **Description**: The DHCP Server role provides automated IP address management.
   - **Steps**:
     1. Open **Server Manager**.
     2. Click on **Add Roles and Features**.
     3. Select **DHCP Server**.
     4. Follow the wizard to install the role.

   - **Example**: Installing DHCP to manage IP address allocation for the "192.168.1.x" subnet.

2. **Create and Configure DHCP Scopes:**
   - **Description**: Scopes define the range of IP addresses the server can assign to clients.
   - **Steps**:
     1. Open **DHCP Manager**.
     2. Right-click on **IPv4**, select **New Scope**.
     3. Follow the wizard to define the scope range, subnet mask, and lease duration.
     4. Configure additional options like DNS servers and gateway addresses.



   - **Example**: Creating a scope for "192.168.1.100 - 192.168.1.200" with a 24-hour lease time.

3. **Configure DHCP Reservations:**
   - **Description**: Reservations ensure specific devices always receive the same IP address.
   - **Steps**:
     1. Open **DHCP Manager**.
     2. Right-click on the appropriate scope, select **Add Reservation**.
     3. Enter the reservation details, including the MAC address of the device.

   - **Example**: Reserving the IP address "192.168.1.150" for a printer with MAC address "00-1A-2B-3C-4D-5E".

4. **Set DHCP Options:**
   - **Description**: Options provide additional configuration settings to clients.
   - **Steps**:
     1. Open **DHCP Manager**.
     2. Right-click on the scope, select **Scope Options**.
     3. Add or modify options like DNS servers, default gateway, and domain name.

   - **Example**: Setting the DNS server option to "192.168.1.1" and the default gateway to "192.168.1.254".

### Troubleshooting

1. **IP Address Conflicts:**
   - **Problem**: Multiple devices receiving the same IP address.
   - **Steps**:
     1. Check the scope settings to ensure there are no overlapping ranges.
     2. Verify that no static IP addresses within the DHCP range are causing conflicts.
     3. Use **IPconfig /all** on clients to check their IP configurations.
     4. Review the DHCP server logs for conflict detections.

   - **Example**: Conflict caused by a static IP address configured within the DHCP range.

2. **Clients Not Receiving IP Addresses:**
   - **Problem**: Devices cannot obtain an IP address from the DHCP server.
   - **Steps**:
     1. Ensure the DHCP server service is running.
     2. Verify that the scope is activated and has available addresses.
     3. Check for network connectivity issues between clients and the DHCP server.
     4. Use **DHCP logs** and **Event Viewer** to identify any server errors.

   - **Example**: Clients not receiving IP addresses due to a deactivated scope or exhausted IP range.

3. **Incorrect IP Address Assignment:**
   - **Problem**: Clients are receiving unexpected IP addresses.
   - **Steps**:
     1. Verify the scope configuration to ensure the correct range is set.
     2. Check if there are multiple DHCP servers on the network causing conflicts.
     3. Ensure that any reservations or exclusions are correctly configured.
     4. Use **IPconfig /release** and **IPconfig /renew** on clients to refresh their IP settings.

   - **Example**: Clients receiving IP addresses from a rogue DHCP server on the network.

---

### Additional Resources

- **Microsoft Docs for AD, DNS, and DHCP**: Detailed guides and best practices.
- **TechNet and Spiceworks**: Community forums and resources for troubleshooting.
- **Lab Environments**: Set up virtual labs to practice configurations and troubleshooting.

These detailed setups and troubleshooting techniques should give you a solid foundation to discuss Microsoft Server Technologies in your interview and handle related tasks effectively.
