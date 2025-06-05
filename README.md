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

