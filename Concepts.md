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

- Application - File transfer, mail services
- Presentation - Data encoding, encryption
- Session - Synchronization of data
- Transport - Service point addressing
- Network - Routing
- Data link - Physical addressing, access control
- Physical - Representation of bits, transmission mode

TCP/IP Model
-
- Stands for Transmission Control Protocol and its a suite of communication protocols used to interconnect network devices on internet
- TCP/IP is used as communications protocol in private computer network
- Keep all layers in OSI as it is
- Application + Presentation + Session :- Application layer
- Then transport layer
- Then network means internet
- Data Link + Physical :- Network access layer
