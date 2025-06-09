Basics of Networking
-
- Infrastructure design :- Setting up networks, configuring routers and firewalls, ensuring servers and other devices are properly connected to design scalable and efficient infrastructure
- Application deployment :- Deployment involves configuring LBs, servers and other network components to ensure application runs smoothly and reliably. Networking knowledge is essential to configure network components and resolving network related issues arising during deployment
- Automation :- Networking automation tools such as ansible/puppet are used to automate comfiguration of network devices and ensure that they're properly configured and maintained.
- Monitoring :- Monitoring network traffic, identifying bottlenecks and performance issues and troubleshooting network related problems

IP Protocol
-
- It is a set of rules that governs how data is sent and received over internet or other networks
- It defines how devices identify each other and how data should be delivered from one device to other
- Data is broken into smaller pieces called "Data Packets". Each packet travels independently through network and may take different routes to reach destination
- Every device has unique IP address

- IPV4 :- most widely used using 32-bit address
- IPV6 :- newer version using 128 bit address to allow more devices to connect

-------------------------------------------------------------------------------------------------------

Protocols
-
- Address Resolution Protocol (ARP)
  - Associates IP address with physical address. On physical network such as LAN, each device on link is identified by physical address printed usually on NIC
  - Anytime host or router need to find physical address of another host on its network, it formats ARP query packet with IP address and broadcast it over network
 
- Internet Control Message Protocol (ICMP)
  - Mechanism used by hosts and routers to send notifications to sender if datagram has problems
 
- File Transfer Protocol (FTP)
  - Network protocol for transmitting files between computers over TCP/IP connections
 
-------------------------------------------------------------------------------------------------------

CIDR Notation
-
- Classless Inter-Domain Routing
- Collection of IP protocols used to generate unique IDs for network and individual devices
- Method for assigning IP addresses and routing IP packets more efficiently. Allows flexible division of IP addresses
- e.g :- 192.168.1.0/24 :- /24 means first 24 bits and network bits
- 2^(32-x)-2 :- 192.168.1.0/24 :- 2^(32-24)-2 = 2^8-2 = 256-2

-------------------------------------------------------------------------------------------------------

DNS
-
- DNS is like phonebook of internet. It translates human readable domain names into IP addresses so computers can understand and connect to each other
- When we type website name, DNS finds corresponding IP so computer loads site.
- Computer checks local DNS cache. If not found it asks recursive DNS resolver(ISP's DNS server). If resolver doesnt know, it asks DNS root servers. Then authoriative DNS server returns IP address and computer connects to IP address to load website

-------------------------------------------------------------------------------------------------------

SSH
-
- SSH encrypts communication
- Used to login remote servers, running commands on remote machines, secure file transfers, forwarding traffic

- Initiate connection from SSH client, then ssh server responds, they negotiate encryption and we get authenticated. Then we get encrypted session
