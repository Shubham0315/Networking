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
