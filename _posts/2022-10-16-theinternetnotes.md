---
title: Big Idea 4 - The Internet Notes
description: Notes taken based on the corresponding CollegeBoard lesson.
toc: true
layout: post
comments: true
hide: false
search_exlude: false
permalink: /theinternetnotes/
---

## Historical Facts

ARPANET (Advanced Research Projects Agency Network) was one of the first networks (1975). Eventually, the need for computers to talk to each other became so great that more efficient ways for them to were developed.

## How Data is Sent and Received

Information is sent over a network in <mark>packets</mark>, which include data including the source of the information and the destination. <mark>Computer systems</mark> are groups of computing devices working together for a joint purpose and <mark>computer network</mark>, a type of computing system, is a group of interconnected computing devices that can send information to each other.

Files sent between devices are chopped up into packets in any order, then read and recreated by the recipient's computer. This is called <mark>packet switching</mark>. Packets need to be used to send data because the amount that's sent between systems is too great to transfer all at once. <mark>Routing</mark> is finding a <mark>path</mark> between devices to transfer information. A path is a sequence of connected computing devices, starting with the sender and ending with the recipient.

When you hear internet providers talking about <mark>bandwidth</mark>, they're referring to how much data can be sent between devices in a given amount of time (typically measured in bits per second, bps).

### Vocabulary Matching Activity

1. A path is a sequence of directly connected computer devices that begins at the sender and ends at the receiver. (a)
2. Routing is the process of finding a path from a sender to a receiver. (b)
3. A computer system is a group of computing devices and programs working together for a common purpose.
4. A computer device is a physical artifact that can run a program (computers, tablets, servers, routers, smart sensors, etc.). (c)
5. Bandwidth is the maximum amount of data that can be sent in a fixed amount of time. (d)
6. A computer network is a group of interconnected computing devices capable of sending or receiving data.

## How the Internet Works

To start with vocab, a <mark>protocol</mark> is a set of rules that determine a system's behavior. The Open System Interconnect (<mark>OSI</mark>) protocol model contains 7 layers of protocols to go through in order to communicate.

<figure>
  <img src="{{site.baseurl}}/images/impervaosimodel.png" alt="OSI Model" width="500"/>
  <figcaption>Via imperva.com</figcaption>
</figure>

Transmission Control Protocol (<mark>TCP</mark>) is what establishes the standards of how messages are sent between devices on the internet. The Internet Engineering Task Force (<mark>IETF</mark>) manages the standards and discussions regarding the internet in a collaborative manner.

<figure>
  <img src="{{site.baseurl}}/images/narrowwaistdiagram.png" alt="Narrow Waist Diagram" width="430"/>
  <figcaption>Via College Board APCSP Big Idea 4 - The Internet, Video 2</figcaption>
</figure>

This diagram from the College Board video, called the "Narrow Waist diagram," shows how the internet works. Let's break it up into chunks.

### Network Access Layer

This layer involves the hardware and protocols that sends the 1's and 0's between devices. The most common of these protocols is <mark>Ethernet</mark>, which is implemented in Network Interface Cards (<mark>NIC</mark>). The delivery of packets between NIC's is called a "hop". Local hops use the NIC's unique Media Access Control (MAC) address.

### Internet Layer

Connecting this layer to the Internet layer are routers, which use the <mark>metadata</mark> in packets to gain information on how to effectively route a path. The path should eventually end at the receiver's IP address. The internet is flexible and scalable, so it is able to meet demands. At this layer, the IP address should be received.

To illustrate, Local Area Networks (<mark>LAN</mark>) can connect 10 to 100 systems. An <mark>intranet</mark> can be 100 to 1000 LAN systems. These intranets want to communicate with each other, so they link together via autonomous systems (<mark>AS</mark>), controlled by internet providers and able to hold tens of thousands of systems. The final stage, the internet, links together AS's to unite millions of systems via special telecommunication (like satellites).

### Transport Layer

The transport layer uses two primary types of protocols: Transmission Control Protocol (<mark>TCP</mark>) (also called Internet Protocol, <mark>IP</mark>) and User Datagram Protocol (<mark>UDP</mark>).

Overall, TCP is more like a certified delivery of information, ensuring that data was sent to its intended recipient and undergoing error checking and correcting protocols; this emphasis on precision makes it a bit slower than UDP to use. It is more often used for things like emailing and web browsing.

UDP, on the other hand, just puts in its best effort to deliver data, discarding erroneous packets found through error checking. It is more often used for things like media streaming.

Your IPv4 address is split into four octets (8 bits each, spanning 256 total values in a zero-based system, so the maximum value is 255). The 32nd bit of the 32 total is a network bit. Using an IP, three targets can be addressed: <mark>unicast</mark>, which is a specific device (internet-wide access, addressed using TCP); <mark>multicast</mark>, which is a set of devices in a specific range of IP addresses (internet-wide access, addressed using UDP); and <mark>broadcast</mark>, which is all devices (LAN-wide access, addressed using UDP).

### Application Layer

This is the layer where the user gets to use easier names for websites to find sites they wish to visit.

<mark>HTTP</mark> is how a computers asks for and receives data from a web server (normally uses TCP, Port 80 at the transport layer). <mark>HTTPS</mark> is basically HTTP but with more security (also uses TCP, Port 443).

Web servers are machine-run programs that provide clients web pages, linked using Uniform Resource Locations (<mark>URL</mark>).

The Domain Name Service (<mark>DNS</mark>) translates URLs to computer-readable IP addresses. DNS holds a database of tons of IP addresses and their corresponding URLs, stored on many large computers.

### Internet and Transport Layers Operation

Here is a diagram found in the College Board video to illustrate the process of internet communication.

<figure>
  <img src="{{site.baseurl}}/images/internettransportlayersoperation.png" alt="Internet Transport Layers Operation" width="600"/>
  <figcaption>Via College Board APCSP Big Idea 4 - The Internet, Video 2</figcaption>
</figure>

### Video 2 True or False Review

<figure>
  <img src="{{site.baseurl}}/images/internetmcreview.png" alt="True or False Review" width="600"/>
  <figcaption>Via College Board APCSP Big Idea 4 - The Internet, Video 2</figcaption>
</figure>

## Expectations from APCSP Page

Here are some things mentioned on the APCSP "Big Idea 4 - The Internet" page that we're supposed to do.

### Domain Name Service

[Here]({{site.baseurl}}/theinternetnotes/#application-layer) is where the College Board materials bring up DNS.

Let's use "sub.domain.com" as an example. The "domain" part is the site's regular domain. The "sub" is a unique subdomain of the site.

Here are screenshots of the A and CNAME records associated with YouTube.

<img src="{{site.baseurl}}/images/youtubednsa.png" alt="DNS A Record" width="500"/>

<img src="{{site.baseurl}}/images/youtubednscname.png" alt="DNS CNAME Record" width="500"/>

The A record seems to show the various IP addresses that you can be directed to when requesting YouTube's domain. The numerous addresses, as the video mentioned, are likely to avoid too much traffic on a single page, considering how much traffic YouTube constantly gets.

### IP Addresses I Use Daily

Here are six, as requested.

MyConnect (Canvas):
- 18.204.109.29
- 3.95.144.229
- 34.202.195.44

Google:
- 142.250.189.196

YouTube:
- 142.250.189.174
- 142.250.189.206
- 142.250.191.46
- ETC...

Google Docs:
- 142.250.191.46

Slack:
- 3.95.117.96
- 34.193.255.5
- 34.203.97.10
- ETC...

Github:
- 140.82.112.3