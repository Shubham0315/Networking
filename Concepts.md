# Computer Networking

- To connect different systems at different locations, network is used. Using network we can transfer data. It is basically a group of networks which is called internet
- Computer networking tells us how our data gets transferred in a network, how it is connected to multiple computers

- If we've to access site in US from India, it is done using optical cables and wires inside sea we can access the site
  - We first send request to the site using browser.
  - We reach the site using http or https protocol. http/s renders all the html/css webpages on browser
  - The files to reach the site are placed on website server which is placed in US which has IP address
  - But in browser we provide only website name. The IP address is understood by DNS
  - Website is mapped with one IP address. DNS servers has the record of server and its IP.

To access site 
- Access internet using optical cable - Send request to website using browser - to reach IP of website DNS resolves the request


traceroute
-
- To check the route of request given by user how it flows
- To reach to netflix.com, first our browser hits request. It goes to our local internet (wifi). Then it goes to ISP address (airtel). Then it goes through multiple IPs/servers and then goes to our website and provides us required data

![image](https://github.com/user-attachments/assets/e65c2e1a-c42c-4344-81b0-bc79c70692f4)

---------------------------------------------------------------------------------------------------

OSI Model
-
- Consist of 7 layers
- Application is run by end user.
- Application(HTTP/HTTPS) - Presentation(Syntax, Security) - Session(API, Sockets) - Transport(TCP) - Network(Packets) - Data Link(Ethernet) - Physical

- Application - File transfer, mail services. Interacts directly with end-user apps
- Presentation - Data encoding, encryption. Translates, encrypts and compresses data
- Session - Synchronization of data. Manages sessions and connections between apps
- Transport - Service point addressing. Provides reliable data transfer and flow control
- Network - Routing. Handles routing and addressing of data
- Data link - Physical addressing, access control. Handles error detection
- Physical - Representation of bits, transmission mode. Transmits bits over physical media

- **Please Do Not Throw Sausage Pizza Away**

TCP/IP Model
-
- Stands for Transmission Control Protocol and its a suite of communication protocols used to interconnect network devices on internet
- TCP/IP is used as communications protocol in private computer network
- Keep all layers in OSI as it is
- Application + Presentation + Session :- Application layer
- Then transport layer
- Then network means internet
- Data Link + Physical :- Network access layer


---------------------------------------------------------------------------------------------------

IP and Subnets
-
-  Acc to TCP/IP protocol, whichever device is on internet has an IP address.
-  In our home we might have 10 devices each having IP address. In our building we might have 1000s of IPs. In a city there can be crores of IPs
-  But we have only 4,294,967,296 IP addresses in world (search on internet). IPV4 are limited. To solve this IPV6 was launched where there are 2^128 (search on internet) 340,282,366,920,938,463,463,374,607,431,768,211,456 which are not less.
- IPV6 is not that much used. IPV4 is mostly in use.
- To overcome limited IPV4, we can have network in which we can create subnetwork which have unique IPs. Inside network there are multiple subnets(mini internet inside internet)
- Subnet is part of network so we get unique address of our device

- So our devices are put into one network which has IP address. So which network we are connected, we get mapped with that IP
- If we disconnect from one network and connect to other, our device gets mapped with new IP

---------------------------------------------------------------------------------------------------

DNS, NAT and Firewalls
-
- While creatig EC2, we get tab of Network Settings
- Go to network settings - Edit

![image](https://github.com/user-attachments/assets/6f29511c-b728-41ec-8147-3340fc3d2609)

- Suppose on internet we have AWS inside which we can create our own network called Virtual Private Cloud (VPC). Also we can have multiple VPCs under one AWS Cloud each with different/isolated networks, IPV4 addresses. Inside the VPC we create our instance which gets IP address. Here devices in 2 VPC can have same IP addresses unlike earlier concepts due to separated/isolated network

![image](https://github.com/user-attachments/assets/054d077d-4717-43ef-86ce-387273d3e701)

- If we've many devices inside our VPC and IP addressed are about to get finished, we can do subnetting.
- So inside the VPC, create a subnet and put devices into it where allocation of IPs to devices is not possible due to limitation.

- So from above image of EC2, we can say there is VPC which has its ID, under which we've subnets. We can auto assign IP address for the subnet. Create firewall so that our server to get access through SSH only (rules)

- Server is created as AWS Cloud - VPC - Subnet - Server

- If we go to Networking section of EC2, we get all the information

![image](https://github.com/user-attachments/assets/48c31fc8-000d-487e-b339-8ede9853b248)

- Connect to the EC2 using AWS UI, it will try to establish connection using OSI model
  - First go to browser, open application - Check presentation security - Maintain session between AWS and browser - Used TCP to transfer data - Connected through Network - We can access app using data link and Physical layer
- After connecting update the system :- **sudo apt-get update**
- Install nginx for making web page :- **sudo apt-get install nginx**
- Webpage location :- **cd /var/www/html**

![image](https://github.com/user-attachments/assets/860c6160-12c5-49bc-bb10-83b59b4241e4)

- Create another webpahge there named "index.html" using chatgpt

![image](https://github.com/user-attachments/assets/50ba1b3d-22ed-4f89-b3fd-8d10762047bc)

- To check nginx server status :- systemctl status nginx

![image](https://github.com/user-attachments/assets/51d58af8-f70d-4114-863d-bb65137c59df)

- Take private IP and enter with 80, we cannot access the site. Our firewall is not allowing to connect to server which is SG or NACL. Go to EC2 - Security - Security groups - Add rule
- To send data to internet, we need TCP IP so select Custom TCP, port should be 80, source to be anywhere IPV4 - Save rule and access the site now with port 80

![image](https://github.com/user-attachments/assets/d8e9fa19-9c7f-489b-bff0-d906b12ba876)
![image](https://github.com/user-attachments/assets/a1173d4d-be42-4981-a355-23d4e08bab7a)

- NAT is Network Address Translation which helps private and public subnets to communicate.
- If we've to map our IPV4 address to domain name, we can do using GoDaddy. Now our IP gets mapped with a DNS so that we get our webpage if we browse for the domain only instead of IP
- We can also get domain from AWS UI - Route53 - Register domain for cheaper price

- Lets say we have VPC under which 2 subnets are there which are public and private. EC2 is in public subnet hosting app which user can access (thus kept in public subnet for user ease). DB of the app lets say RDS which is kept in private subnet. Now for resources in private subnet we need to access from public subnet which is not enabled by default. For this we need to translate IP of both subnets where we use NAT Gateway - Network Address Translation
- So we'll connect our public subnet device with NAT gateway and it will translate address and connect to DB. Same for DB if it has to access app in public subnet, NAT gateway is to be used

- Now our VPC is in AWS cloud and user is in outside network. Both have different networks. Can user acccess the application directly? ---- NO
  - Here AWS has VPC which has different network. So we need another gateway for outside world -- Internet Gateway
  - IGW will connect with our VPC first. There we need route tables to connect with different subnets which takes our request to our application
 
  - User request - Internet Gateway - Route Table - Application(public) - NAT Gateway - DB (Private)
 
![image](https://github.com/user-attachments/assets/591d508c-2644-49bc-a38a-eaf168f97650)

  - The route provides access ti different subnets as per above diagram

- Create VPC - Create subnet - Create IFW - Create route tables and associate subnet with it

---------------------------------------------------------------------------------------------------

- To connect 2 VPCs with each other is called as VPC peering

---------------------------------------------------------------------------------------------------

Load Balancer
-
- It is a gateway which distributes traffic to the application
- Application LB and Network LB and Gateway LB
- In EC2, we can create LB
- ALB is used to redirect HTTP/S traffic, network LB works on VPC level

- LB is a device or software that distributes incoming traffic across multiple servers to ensure no single server is overloaded. It routes client requests to the most appropriate backend server
- LB is used to have high availability, scalability to distribute traffic evenly, performance and security of apps

- Client request to LB IP - LB decides server to route the request - Request is routed to server - Server processes request and sends response back to client through LB

- Types of LB algorithms :-
  - Round robin
  - Least connections - send traffic to server with fewest active connections
  - IP Hash - uses client IP to decide which server to route the request
  - Weighted round robin - servers get more traffic based on capacity
 
- Types of LB :-
  - Application LB :- Layer 7 of OSI. Has content based routing (path/host based). Supports HTTP/S. Ideal for microservices and container-based apps
  - Network LB :- Transport layer Layer 4. Handles millions of requests/second. Very low latency. Can handle sudden traffic spikes
  - GateWay LB :- Transport proxy at network layer. Routes traffic to third party virtual appliances like security appliances, firewalls, inspection tools

