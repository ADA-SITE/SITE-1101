# 07-08. The Internet and the World Wide Web

!!! info
    - Nilufar Ismayilova, Rumiyya Alili, Ismayil Shahaliyev
    - Nov 21 2025 / Dec 23 2025

## The Internet

The [Internet](https://en.wikipedia.org/wiki/Internet) is a global network of interconnected computer networks that allows devices around the world to communicate. It is not controlled by any single organization; instead, many independent networks—such as home networks, university networks, company networks, and government networks—connect to each other voluntarily. Together, these connections form a large, [decentralized](https://en.wikipedia.org/wiki/Decentralized_computing) system that enables information to travel quickly and reliably between distant points.

For communication to be possible across such a system, all connected devices must follow common rules. These rules are called **network protocols**. A _protocol_ defines how data is sent, in what format, in what order, and what happens if errors occur. Without protocols, networks could be physically connected, but devices would not understand each other.

The Internet follows a hierarchical structure. Local networks connect to Internet Service Providers (ISPs), which then connect to larger regional networks and finally to high-speed backbone networks that carry data across countries and continents. When you open a website or send a message, your data travels through this chain of networks according to agreed-upon protocols until it reaches its destination.

## Internet Protocol Suite

The [Internet Protocol Suite](https://en.wikipedia.org/wiki/Internet_protocol_suite), commonly known as **TCP/IP**, is the foundational set of communication rules that defines how data is prepared, addressed, transmitted, and received across the Internet. It organizes network communication into layers, where each layer performs a specific part of the process.

At the core is the [Internet Protocol (IP)](https://en.wikipedia.org/wiki/Internet_Protocol), which assigns addresses to devices and routes data packets from the sender to the correct destination, even if they pass through many different networks. Above IP, the suite includes transport protocols that manage how data is broken into smaller pieces, how those pieces travel, and how they are reassembled when they reach the receiver.

[TCP (Transmission Control Protocol)](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) and [UDP (User Datagram Protocol)](https://en.wikipedia.org/wiki/User_Datagram_Protocol) are the two main transport protocols. TCP provides reliable, ordered, error-checked delivery. It establishes a connection, confirms delivery, and retransmits lost packets. TCP is used when accuracy matters, such as loading websites, sending emails, or downloading files. UDP is faster but does not provide guaranteed delivery or ordering. Lost packets are not retransmitted. UDP is used for real-time applications where speed matters more than perfect accuracy, such as video calls, online gaming, and live streaming.

!!! note
    When you visit a website, your request is divided into packets and routed across multiple networks to the server’s IP address. Because web traffic uses TCP, packets are delivered reliably and reassembled in order. In a video call, UDP may be used instead to avoid delays caused by retransmissions.

## IP Address

[IP addressing](https://en.wikipedia.org/wiki/IP_address) uniquely identifies devices on a network so routers know where to deliver packets. An IP address functions like a postal address: it identifies the destination and the sender.

IPv4 uses 32 bits, written as four decimal numbers separated by dots, such as `192.168.1.4`. IPv6 uses 128 bits, written as hexadecimal blocks separated by colons, such as `2001:db8:85a3::8a2e:370:7334`. IPv6 was introduced because the IPv4 address space is too small for the number of modern devices.

**Exercise.** How many unique addresses are possible with IPv4? What about IPv6?

## Domain Name System

The [Domain Name System (DNS)](https://en.wikipedia.org/wiki/Domain_Name_System) translates human-readable domain names into IP addresses. Without DNS, users would have to memorize numerical IP addresses for websites.

DNS is hierarchical. At the top is the root domain (`.`), usually hidden. Under it are top-level domains (TLDs) such as `.com`, `.az`, `.org`. Under each TLD are second-level domains such as `edu.az`. Subdomains further divide these, such as `ada.edu.az` or `library.ada.edu.az`.

!!! note
    When you type `www.ada.edu.az`, your computer asks DNS for the IP address. DNS returns the IP, and the browser connects to that server. This lookup happens automatically in the background.

## Routing

[Routing](https://en.wikipedia.org/wiki/Routing) is the process by which routers determine paths for data packets to travel across networks from source to destination. Internet traffic usually passes through multiple routers, and each router decides where to send the packet next.

**Static routing** is configured manually. It is predictable and simple but does not adapt if a link fails.

**Default routing** sends any unknown destination to a single next-hop router. Home networks often use default routing to send all external traffic to the ISP.

**Dynamic routing** uses protocols that let routers exchange information and update routes automatically based on network conditions. This is essential for large networks and the Internet backbone.

!!! note
    If one route becomes congested or unavailable, dynamic routing helps traffic flow through alternative paths automatically.

## OSI Model

The [OSI (Open Systems Interconnection) model](https://en.wikipedia.org/wiki/OSI_model) explains networking using seven layers. Each layer has a specific role and interacts with the layer above and below it.

| # | Layer | Function | Example |
|---|-------|----------|---------|
| 7 | Application | Services used by applications; protocols like HTTP, DNS, FTP, SMTP | Browser uses HTTP to request a webpage; DNS resolves a domain name |
| 6 | Presentation | Data format translation, compression, encryption/decryption (TLS/SSL) | HTTPS encrypts data so attackers cannot read passwords |
| 5 | Session | Establishes and manages communication sessions | A video call maintains a session so streams stay coordinated |
| 4 | Transport | End-to-end delivery; TCP reliability, UDP low overhead | Web pages use TCP; games often use UDP |
| 3 | Network | Routing between networks; IP addressing | Routers forward packets using destination IP addresses |
| 2 | Data Link | Local delivery; framing; MAC addresses; link-level error detection | Wi-Fi/Ethernet frames addressed to the local router’s MAC |
| 1 | Physical | Transmits raw bits via signals over cable, fiber, or radio | Wi-Fi radio waves; Ethernet electrical pulses |

!!! note
    When you open a website, the browser starts at the Application layer (HTTP). If it is HTTPS, encryption is applied. TCP carries the request reliably. IP routes it across networks. Wi-Fi/Ethernet handles local delivery, and the physical medium transmits signals.

## World Wide Web

The [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web) is a global information system of web pages and services accessed through browsers. The Internet is the network infrastructure; the Web is one service that runs on it. Web pages are connected through [hyperlinks](https://en.wikipedia.org/wiki/Hyperlink) and are typically written in [HTML](https://en.wikipedia.org/wiki/HTML). Browsers request resources from web servers and render them for users.

[Hypertext Transfer Protocol (HTTP)](https://en.wikipedia.org/wiki/HTTP) defines how browsers request resources and how servers respond. Servers return status codes such as `200 OK` or `404 Not Found`.

Most modern sites use [HTTPS](https://en.wikipedia.org/wiki/HTTPS), which is HTTP plus encryption using [TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security). This protects sensitive data (passwords, payments, personal information) from interception and modification.

!!! note
    When you sign in to a website, HTTPS encrypts your credentials so someone on the same Wi-Fi network cannot read them.

A [Uniform Resource Locator (URL)](https://en.wikipedia.org/wiki/URL) is the full address of a web resource. It includes the protocol, domain, path, and optional query parameters.

- `https` is the protocol  
- `www.ada.edu.az` is the domain name  
- `/en/search` is the path  
- `?query=SITE` is a query parameter  

## Markup Languages

Markup languages annotate text so computers can understand structure and presentation.

[HTML](https://en.wikipedia.org/wiki/HTML) structures web pages using tags such as `<h1>`, `<p>`, and `<img>`.

[XML](https://en.wikipedia.org/wiki/XML) stores and transports structured data using custom tags, often for configuration and interoperability.

[JSON](https://en.wikipedia.org/wiki/JSON) is a lightweight data format using key-value pairs. It is widely used in APIs and web applications because it is simple and efficient.

!!! note
    A website uses HTML for what the browser displays. A web application often uses JSON behind the scenes to exchange data between the frontend and backend.

## Intranet and Extranet

An [intranet](https://en.wikipedia.org/wiki/Intranet) is a private network used inside an organization. It provides internal services such as employee portals, shared files, calendars, and internal communication.

An [extranet](https://en.wikipedia.org/wiki/Extranet) extends an intranet by granting limited access to external users such as partners, suppliers, contractors, or students. Access is controlled through accounts, permissions, or [VPN](https://en.wikipedia.org/wiki/Virtual_private_network).

!!! note
    A company intranet may host internal HR and financial documents. An extranet may allow a contractor to access only a shared project folder and schedule, not the full internal system.

## Cloud Computing

[Cloud computing](https://en.wikipedia.org/wiki/Cloud_computing) delivers computing resources—servers, storage, databases, networking, and software—over the Internet. Instead of buying and maintaining hardware, organizations rent resources on demand. This enables scalability, flexibility, and pay-as-you-go cost models.

Cloud services are often grouped into three models:

- [Infrastructure as a Service (IaaS)](https://en.wikipedia.org/wiki/Infrastructure_as_a_service): virtual machines, storage, networking
- [Platform as a Service (PaaS)](https://en.wikipedia.org/wiki/Platform_as_a_service): managed platforms for building and deploying apps
- [Software as a Service (SaaS)](https://en.wikipedia.org/wiki/Software_as_a_service): ready-to-use applications delivered via browser

!!! note
    Email services, online storage, and learning platforms are common SaaS examples. Renting virtual machines to host a website is an IaaS example.

## Centralized, Decentralized, Distributed Systems {#centralized}

A [centralized system](https://en.wikipedia.org/wiki/Centralized_computing) relies on a single central authority or server. It is simpler to manage but fragile: if the central point fails, the whole system may stop.

A [decentralized system](https://en.wikipedia.org/wiki/Decentralised_system) has multiple independent authoritative nodes. If one node fails, others can continue operating. The Internet is decentralized at the network level.

A [distributed system](https://en.wikipedia.org/wiki/Distributed_computing) splits computation and storage across many nodes that coordinate to function as one system. Distributed systems emphasize scalability, performance, and fault tolerance.

<img src="../../assets/images/lecture09/image.png" alt="Centralized vs decentralized vs distributed" style="max-width: 100%; height: auto;">

In short, centralized means one control point, decentralized means multiple independent control points, and distributed means many coordinated components working together. These concepts overlap in practice but describe different design trade-offs.

## Additional Material

- [What is Internet?](https://www.youtube.com/watch?v=Dxcc6ycZ73M)
- [The Internet: Crash Course Computer Science #29](https://www.youtube.com/watch?v=AEaKrq3SpW8)
- [Public vs Private IP Address](https://www.youtube.com/watch?v=po8ZFG0Xc4Q)
- [How a DNS Server (Domain Name System) works](https://www.youtube.com/watch?v=mpQZVYPuDGU)
- [TCP vs UDP Comparison](https://www.youtube.com/watch?v=uwoD5YsGACg)
- [Network Layers Model (Networking Basics) - Computerphile](https://www.youtube.com/watch?v=eelvWAURfdI)
- [VPN (Virtual Private Network) Explained](https://www.youtube.com/watch?v=R-JUOpCgTZc)
- [The World Wide Web: Crash Course Computer Science #30](https://www.youtube.com/watch?v=guvsH5OFizE)
- [What is the world wide web? - Twila Camp](https://www.youtube.com/watch?v=J8hzJxb0rpc)
- [How trees secretly talk to each other - BBC World Service](https://www.youtube.com/watch?v=DUqEB_tGHtw)
- [SSL, TLS, HTTP, HTTPS Explained](https://www.youtube.com/watch?v=hExRDVZHhig)
- [HTTP Crash Course & Exploration](https://www.youtube.com/watch?v=iYM2zFP3Zn0)
- [HTTP 1 vs HTTP 2 vs HTTP 3!](https://www.youtube.com/watch?v=UMwQjFzTQXw)
- [DHCP Explained - Dynamic Host Configuration Protocol](https://www.youtube.com/watch?v=e6-TaH5bkjo)
- [Cloud Computing Explained](https://www.youtube.com/watch?v=_a6us8kaq0g)
- [How to Setup VS Code for Web Development (2025) HTML, CSS, JavaScript + Live Server](https://www.youtube.com/watch?v=xkMfMJn5Smg)
- [Every File Format Explained in 16 Minutes](https://www.youtube.com/watch?v=pNWL59tB7Z0)
