# Networking

Create EC2 for the demo and connect to it

Ping
-
- Command which tells us that data is getting transferred on particular VM or server and we're getting data back (Request and Response)
- Command :- **ping amazon.com**
- Ping command sends and receives the data in the form of packets. Packet consist of data which helps in transmission.

![image](https://github.com/user-attachments/assets/5f25d99e-fb75-42d8-886b-83ca2ad13c86)

Netstat
-
- Network statistics. All info about our network
- This comes under tool named "net-tools" which we need to install.

![image](https://github.com/user-attachments/assets/e7a8cab9-8bca-4491-b373-d99265d85647)

- Netstat provides active internet connections on system and protocols present
- Here we've connected to EC2 from system (using SSH). Here the internet transfer is through wifi (Foreign Address). TCP for data transfer protocol. Local address means our local
- If we change our wifi connection to mobile hotspot, our foreign address will change

![image](https://github.com/user-attachments/assets/f17ffe95-324d-4d2b-acfe-f5ebce206e4c)

- While using EC2, there are many sockets which are for connecting system with another system or interface.
  - Bus socket
 
ifconfig
-
- Interface where we get list of all network interfaces. If we install docker, etho, it will create its own network interface and show us
- For any app, we get info of all NIC (Network Interface Card) on instance with private IP and other details

![image](https://github.com/user-attachments/assets/c7bb7278-f818-45e4-a1e4-3be90be7a173)

- lo we see above is loopback. If we dont have NIC on server still we can use it as server only means we can access locally like localhost.

Traceroute and Tracepath
-
- We send request to website using our ISP which sends request to server of website where DNS resolves the request (IP of youtube) and then our request reaches the website and we get response back. This is route
- To trace the route we use "TRACEROUTE"
- Comamnd :- **traceroute youtube.com**
- Traceroute goes to EC2 IP address from our local. Then goes to one by one server and then reaches to youtube server IP (last IP on terminal).
- Going from one server to another :- Hopping

- To get path of website :- **tracepath youtube.com**
- It will give insights of how request flows for traceroute
- If we get no reply in terminal output means its taking time to process

- These commands provides latency issue.

mtr
-
- my trace route
- If we dont want to run ping and tracepath separately, we can run mtr
- It will ping the website and provides path as well
- Command :- **mtr youtube.com**

![image](https://github.com/user-attachments/assets/806fcf9d-02e5-4275-9c92-963557c9d013)


nslookup
- 
- To check if any domain is active and working properly
- Command :- **nslookup youtube.com**
- It gives our server and address of website with IP and name address (2 IPs, 2nd is private IP means HTTPS 443 and 1st is of HTTP 80, this is for any website)

![image](https://github.com/user-attachments/assets/78c5bf6d-2ea1-4230-856a-15629768ad62)
![image](https://github.com/user-attachments/assets/f98d6b63-3afb-4a43-9b19-85069cef6b02)

telnet
- 
- Command :- **telnet youtube.com 80**
- It gives IP of website

![image](https://github.com/user-attachments/assets/65b0d7d2-c0a9-43c3-9bba-8993be7e1074)

hostname 
- 
- To get hostname of system
- We can change hostname by changing contents in file named :- /etc/hosts

iwconfig
-
- Shows all wireless connections for the server

![image](https://github.com/user-attachments/assets/46f506f4-d2f0-4d9a-9c16-017d625744a4)

ss
-
- Version of netstat
- Same as netstat

dig
-
- To get info of IP address of any domain, where it is hosted
- Command :- **dig amazon.com**
- We are trying to get info of amazon.com from ubuntu server

![image](https://github.com/user-attachments/assets/22d3ab05-4632-462c-a21f-a2a32ebf1df2)

whois
-
- To get in depth info about form where the domain name is purchased, where registry is done
- Command :- whois amazon.com

![image](https://github.com/user-attachments/assets/de4507b2-513b-463a-a978-f6f91d35f10a)
![image](https://github.com/user-attachments/assets/e30e60ef-6523-45ef-aabe-2c3a7fa6d6f8)

nc
- netcat

arp
-
- To find mac address of anything

ifplugstatus
-
- To check whether our interface are working or not

------------------------------------------------------------------------------------------------------------------------------------------

curl and wget
-
- curl is to call our API endpoints which in turn gives response from server
- We tell API to get the things to us (response)
- Command :- **curl -X GET https://dummy.restqapiexample.com/api/v1/employees**
- -X GET means we want to get data

![image](https://github.com/user-attachments/assets/5a6d174c-46b2-42a0-a4c3-dfdc21045ae1)

- To get data in good UI way, make more good looking, use below
  - Command :- **curl -X GET https://dummy.restqapiexample.com/api/v1/employees | jq**
 
![image](https://github.com/user-attachments/assets/4c70f621-d5ee-4756-8013-ec94871eb5e6)

- wget is to download things from internet
- Command :- wget $link

![image](https://github.com/user-attachments/assets/983f3ffe-04a4-4401-bc88-32ff6ba0d16c)

iptables
-
- 
 

