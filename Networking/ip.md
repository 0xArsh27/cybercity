# IP Addressing & Subnetting – Cybersecurity Focused Notes

## What is an IP Address
An IP address is a logical identifier assigned to a device on a network to enable communication. In cybersecurity, IP addresses are used to identify assets, attackers, victims, and traffic flow.

---

## Types of IP Addresses

### IPv4
- 32-bit address
- Written in dotted decimal (e.g., 192.168.1.1)
- Total addresses ≈ 4.3 billion
- Widely used in real networks and security tools

### IPv6
- 128-bit address
- Written in hexadecimal (e.g., 2001:db8::1)
- Designed to overcome IPv4 exhaustion
- Important in modern cloud and enterprise environments

---

## Public vs Private IP Addresses

### Public IP
- Globally routable on the internet
- Assigned by ISP
- Used to identify an organization or home network
- Important for attribution and threat intelligence

### Private IP (RFC 1918)
Used inside internal networks and not routable on the internet.
- 10.0.0.0 – 10.255.255.255
- 172.16.0.0 – 172.31.255.255
- 192.168.0.0 – 192.168.255.255

Security relevance:
- Internal scanning
- Lateral movement
- Network segmentation

---

## Static vs Dynamic IP Addresses

### Static IP
- Manually assigned
- Does not change
- Used for servers, firewalls, routers
- Easier to target but easier to monitor

### Dynamic IP (DHCP)
- Assigned automatically
- Changes over time
- Common for user devices
- Makes attribution harder in investigations

---

## How IP Addresses Are Assigned

### ISP Assignment
- ISPs receive IP ranges from RIRs (ARIN, RIPE, APNIC)
- Public IP is assigned to customer router

### DHCP (Dynamic Host Configuration Protocol)
- Assigns IP, subnet mask, gateway, DNS
- Uses ports UDP 67 (server) and UDP 68 (client)

Security risks:
- Rogue DHCP servers
- DHCP starvation attacks

---

## Classification of IP Addresses

### Based on Functionality
- **Unicast**: One-to-one communication. Used for identifying a single device on the network.
- **Multicast**: One-to-many communication. Used for streaming and group communication.
- **Broadcast**: One-to-all communication within the same network. Used for discovery protocols like ARP.

### Based on Accessibility
- **Public IP**: Globally accessible and routable on the internet. Used for external communication.
- **Private IP**: Restricted to internal networks. Used for internal communication and security.
- **Loopback IP**: Used for testing and diagnostics (e.g., 127.0.0.1 in IPv4).

---

## How IP Addresses Are Assigned in Cybersecurity Context

### Static Assignment
- Used for critical infrastructure like servers, firewalls, and routers.
- Ensures consistent addressing for monitoring and access control.
- Security Tip: Document and restrict access to static IPs.

### Dynamic Assignment
- Common for user devices and temporary systems.
- Security Tip: Monitor DHCP logs for unusual activity.

### Reserved IPs
- Certain IP ranges are reserved for specific purposes (e.g., 0.0.0.0/8 for default routes, 169.254.0.0/16 for APIPA).
- Security Tip: Be aware of reserved ranges to identify misconfigurations or malicious activity.

---

## Subnetting Basics
Subnetting divides a large network into smaller logical networks (subnets).

Purpose:
- Reduce broadcast traffic
- Improve performance
- Enhance security isolation
- Control access between network segments

---

## Subnet Mask
Defines which portion of an IP address is network and which is host.

Examples:
- 255.255.255.0 = /24
- 255.255.0.0 = /16

CIDR notation is commonly used in security tools.

---

## CIDR (Classless Inter-Domain Routing)

---

## IP Address Assignment and Their Purposes

### Public IPs
- Assigned to devices that need to communicate over the internet.
- Examples: Web servers, email servers, cloud services.
- Purpose: Enables global accessibility and communication.

### Private IPs
- Assigned to devices within a local network.
- Examples: Computers, printers, IoT devices in a home or office.
- Purpose: Facilitates internal communication and enhances security by isolating internal traffic from the internet.

### Loopback IPs
- Assigned to the loopback interface of a device.
- Examples: 127.0.0.1 in IPv4, ::1 in IPv6.
- Purpose: Used for testing and diagnostics within the same device.

### Reserved IPs
- Assigned for specific purposes as defined by standards.
- Examples:
  - 0.0.0.0/8: Default route.
  - 169.254.0.0/16: Automatic Private IP Addressing (APIPA).
  - 192.0.2.0/24: Documentation and examples.
- Purpose: Avoids conflicts and ensures proper functioning of network protocols.

### Dynamic IPs
- Assigned temporarily by DHCP servers.
- Examples: IPs assigned to laptops, smartphones, and other user devices.
- Purpose: Efficient utilization of IP addresses and simplified management.

### Static IPs
- Manually assigned to devices.
- Examples: Servers, network printers, and critical infrastructure.
- Purpose: Ensures consistent addressing for reliable access and monitoring.

---

## Advanced Cybersecurity Concepts Related to IP Addressing

### IP Spoofing
- **Definition**: IP spoofing involves forging the source IP address in packets to impersonate another device.
- **Purpose**: Used in attacks like DDoS, man-in-the-middle, and session hijacking.
- **Mitigation**: Implement packet filtering (e.g., ingress and egress filtering) to detect and block spoofed packets.

---

### IP Blacklisting and Whitelisting
- **Blacklisting**: Blocking specific IP addresses known for malicious activity.
- **Whitelisting**: Allowing only trusted IP addresses to access resources.
- **Use Cases**: Firewalls, intrusion prevention systems (IPS), and web application security.
- **Tip**: Regularly update lists to ensure effectiveness.

---

### Geolocation and IP Intelligence
- **Geolocation**: Mapping IP addresses to physical locations.
- **Applications**: Threat intelligence, identifying suspicious activity from unusual locations.
- **Tools**: MaxMind GeoIP, IP2Location.
- **Tip**: Combine geolocation with behavioral analysis for better accuracy.

---

### Network Address Translation (NAT)
- **Definition**: NAT translates private IP addresses to a public IP address for internet communication.
- **Types**: Static NAT, Dynamic NAT, and PAT (Port Address Translation).
- **Security Benefits**: Hides internal network structure, reduces attack surface.
- **Tip**: Use NAT in combination with firewalls for enhanced security.

---

### IP Address Scanning Tools
- **Purpose**: Identify active IPs, open ports, and services in a network.
- **Popular Tools**:
  - **Nmap**: Network scanning and vulnerability detection.
  - **Angry IP Scanner**: Lightweight IP scanning tool.
  - **Masscan**: High-speed port scanner.
- **Tip**: Use scanning tools responsibly and ensure proper authorization.

---

### IPv6 Security Considerations
- **Benefits**: Larger address space, built-in IPsec for encryption and authentication.
- **Challenges**:
  - Lack of familiarity among administrators.
  - Potential misconfigurations.
  - New attack vectors like IPv6-specific DoS attacks.
- **Mitigation**: Train staff, monitor IPv6 traffic, and use IPv6-aware security tools.
