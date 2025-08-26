> [!TIP]
> Explore the article on [XiaolinCoding Network Chinese Simplifed](https://www.xiaolincoding.com/network/). GitHub can be found [here](https://github.com/xiaolincoder/CS-Base)

# References and learning resouces
Just to claim that the contents of the network basic is concluded by viewing below resources:
* [How does Internet Work](https://cs.fyi/guide/how-does-internet-work)
* [The Internet Explanied](https://www.vox.com/2014/6/16/18076282/the-internet)

# In the Very Beginning
A **network** is a group of computers or other devices which are connected to eachother.
The core of the **internet** is a global network of interconnected routers, which are responsible for directing traffic between different devices and systems using a set of standardized protocols.These protocols define how information is exchanged between devices and ensure that data is transmitted reliably and securely.

# Terminology Cheatsheet
* Packet: A small unit of data that is transmitted over the internet.
* Router: A device that directs packets of data between different networks.
* IP (Internet Protocol) Address: A unique identifier assigned to each device on a network, used to route data to the correct destination.
* Domain Name: A human-readable name that is used to identify a website, such as google.com.
* NDS (Domain Name System): The Domain Name System is responsible for translating domain names into IP addresses.
* ICANN([Internet Corportation for Assignned Names and Numbers](https://www.icann.org/)): a non-profit organization based in California, mission is to help ensure a stable, secure, and unified global Internet. To reach another person on the Internet, you need to type an address – a name or a number – into your computer or other device. That address must be unique so computers know where to find each other.
* HTTP (Hyper Text Transfer Protocol): used to transfer data between a client (such as a web browser) and a server (such as a website).
* HTTPS(Hyper Text Transfer Protocol Secured): An encrypted version of HTTP that is used to provide secure communication between a client and server.
* SSL (Secure Sockets Layer): is a family of encryption technologies that allows web users to protect the privacy of information they transmit over the internet.
* TLS (Transport Layer Security): protocols to provide secure communication over the internet.
* IP (Internet Protocol): the protocol responsible for routing packets of data to their correct destination.
* TCP (Transmission Control Protocol)
* UDP (User Data Protocol)
* Ports: Ports are used to identify the application or service running on a device. Each application or service is assigned a unique port number, allowing data to be sent to the correct destination.
* Sockets: A socket is a combination of an IP address and a port number, representing a specific endpoint for communication. Sockets are used to establish connections between devices and transfer data between applications.
* Connections: A connection is established between two sockets when two devices want to communicate with each other. During the connection establishment process, the devices negotiate various parameters such as the maximum segment size and window size, which determine how data will be transmitted over the connection.
* Data transfer: Once a connection is established, data can be transferred between the applications running on each device. Data is typically transmitted in segments, with each segment containing a sequence number and other metadata to ensure reliable delivery.
* FTP(File Transfer Protocol)
* SMTP (Simple Mail Transfer Protocol)

SSL(Secure Sockets Layer)/TLS(Transport Layer Security) protocols:
* Certificates: SSL/TLS certificates are used to establish trust between the client and server. They contain information about the identity of the server and are signed by a trusted third party (a Certificate Authority) to verify their authenticity.
* Handshake: During the SSL/TLS handshake process, the client and server exchange information to negotiate the encryption algorithm and other parameters for the secure connection.
* Encryption: Once the secure connection is established, data is encrypted using the agreed-upon algorithm and can be transmitted securely between the client and server.

# Specific Topics
## Package
A packet is the basic unit of information transmitted over the internet. Splitting information up into small, digestible pieces allows the network’s capacity to be used more efficiently.

A packet has two parts. The header contains information that helps the packet get to its destination, including the length of the packet, its source and destination, and a checksum value that helps the recipient detect if a packet was damaged in transit. After the header comes the actual data. A packet can contain up to 64 kilobytes of data, which is roughly 20 pages of plain text.

If internet routers experience congestion or other technical problems, they are allowed to deal with it by simply discarding packets. It’s the sending computer’s responsibility to detect that a packet didn’t reach its destination and send another copy.

## IP v4 vs v6


## TCP

IP UDP FTP SFTP

IP v4 vs IP v6

