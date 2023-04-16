---
toc: true
comments: true
layout: post
title: Computers and Networks Work for Big Idea 4
description: A bunch of work for Big Idea 4
categories: []
---

## Requirements

> Work through College Board Unit 4... blog, add definitions, and pictures.  Be creative, for instance make a story of Computing and Networks that is related to your PBL experiences this year.

### How a Computer Works

> As we have learned, a computer needs aa program to do something smart.  The sequence of a program initiates a series of actions with the computers Central Processing Unit (CPU). This component is essentially a binary machine focussing on program instructions provided.  The CPU retrieives and stores the data it acts upon in Random Access Memory (RAM). Between the CPU, RAM, and Storage Devices a computer can work with many programs and large amounts of data.

List specification of your Computer

- Processor GHz: 3.3 (3.3 GHz Dual-Core Intel Core i7)
- Memory in GB: 16 (16 GB 2133 MHz LPDDR3)
- Storage in GB: 251 GB of total Flash Storage (195 GB allocated to the Mac HD, 55.68 GB to BOOTCAMP)
- OS: macOS Catalina version 10.15.7 (19H15)

#### Diagrams

Define or describe usage of Computer using Computer Programs. Pictures are preferred over a lot of text.  Use your experience.

- Input devices
- Output devices

![Input and output devices]({{site.baseurl}}/images/desktop-computer-with-display-keyboard-mouse-and-printer-on-desk-P3YX9C.jpeg)

- Program File
- Program Code

![Program File vs Program Code]({{site.baseurl}}/images/Product.png)

- Processes

![Processes]({{site.baseurl}}/images/Screen Shot 2023-04-07 at 3.06.44 PM.png)

These are the concurrent processes that were going on on my laptop when I took the screenshot. Processes are essentially areas of program activity, which often run parallel to one another (as long as they aren't dependent on one another, or certain independent processes will run with given space while other room is left for necessarily sequential tasks).

- Ports

These are communication endpoints in web servers that allow them to send and receive data from other sources. A single computer can run many different ports as long as they do not overlap, and they can be used to differentiate between different programs being run on the same computer.

Port 80 is usually used for HTTP traffic and port 443 for HTTPS traffic.

- Data File

![Data files]({{site.baseurl}}/images/Data Files.png)

I've been sharing diagrams in the form of data files throughout this blog.

- Inspect Running Code
- Inspect Variables

![Inspect variable]({{site.baseurl}}/images/Screen Shot 2023-03-17 at 7.27.15 PM.png)

The screenshot above shows variables from a time that we were inspecting code live. I decided to connect back to previous lessons specifically in reference to this.

Inspect running code: The process of analyzing and examining the source code of a program that is currently running to identify errors, optimize performance, or better understand how the program functions.

Inspect variables: The process of examining the values of variables that are being used by a program to identify issues or optimize performance. This can be done through debugging tools or other software that allows for real-time inspection of program variables. I have most often used the console in inspect element (especially working with frontend) and the VSCode debug option (when working with backend). In this case, the SQLite3 `connection` object.

### The Internet

> Watch/review College Board Daily Video for 4.1.1

- Essential Knowledge
    - A computing device is a physical artifact that can run a program. Some examples include computers, tablets, servers, routers, and smart sensors.
    - A computing system is a group of computing devices and programs working together for a common purpose.
    - A computer network is a group of interconnected computing devices capable of sending or receiving data.
    - A computer network is a type of computing system. 
    - A path between two computing devices on a computer network (a sender and a receiver) is a sequence of directly connected computing devices that begins at the sender and ends at the receiver.
    - Routing is the process of finding a path from sender to receiver.
    - The bandwidth of a computer network is the maximum amount of data that can be sent in a fixed amount of time.
    - Bandwidth is usually measured in bits per second

#### 4.1.1 Vocabulary

- Complete Vocabulary Matching Activity. Incorporate this into your learnings from year.
    - Path
    - Route
    - Computer System
    - Computer Device
    - Bandwidth
    - Computer Network

![The Internet Vocab Matching]({{site.baseurl}}/images/Screen Shot 2023-04-15 at 10.17.14 AM.png)

These are all integral aspects of the functionality of the internet and computers, so these terms' relation to our learnings throughout the year is very broad.

One way to view it is in terms of how they relate to a CRUD program that connects a frontend (in our class, I'll say hosted on GitHub Pages) and a backend (let's say Flask on an AWS container). The link to the frontend page, "http://whatever.github.io/frontend/", acts as a descriptor for the <mark>path</mark> that needs to be taken to access it. The Internet Protocol (IP) tells systems how to <mark>route</mark> messages between each other, which had been broken down into packets and are then reconstructed by the network. This is able to occur thanks to the <mark>computer network</mark> that connects computers and servers that hold information.

The <mark>computer system</mark> and <mark>computer device</mark> vocab are ever-present, but don't make a specific contribution in our learning. We use our laptops, our computer devices, in class, and take advantage of the many things they offer in terms of personalization.

> Watch/review College Board Daily Video 4.1.2

#### The Internet True of False

- Complete True of False Questions

![The Internet True or False]({{site.baseurl}}/images/internetmcreview.png)

- Essential Knowledge
    - The internet is a computer network consisting of interconnected networks that use standardized, open (nonproprierary) communication protocols.
    - Access to the internet depends on the ability to connect a computing device to an internet connected device.
    - A protocol is an agreed-upon set of rules that specify the behavior of a system.
    - The protocols used in the internet are open, which allows users to easily connect additional computing devices to the internet.
    - Routing on the internet is usually dynamic; it is not specified in advance
    - The scalability of a system is the capacity for the system to change in size and scale to meet new demands.
    - The internet was designed to be scalable
    - Information is passed through the internet as a data stream. Data streams contain chunks of data, which are encapsulated in packets. 
    - Packets contain a chunk of data and metadata used for routing the packet between the origin and the destination on the internet, as well as for data reassembly.
    - Packets may arrive at the destination in order, out of order, or not at all
    - IP, TCP and UDP are common protocols used on the internet.
    - The world wide web is a system of linked pages, programs, and files.
    - HTTP is a protocol used by the world wide web
    - The world wide web uses the internet

#### Internet Diagram

- Go over AP videos, vocabulary, and essential knowledge.  Draw a diagram showing the internet and its many levels. A preferred diagram would using your knowledge of frontend, backend, deployment, etc.  Picture would highligh vocabulary by illustration. The below illustration have some ideas

![The Internet True or False]({{site.baseurl}}/images/The Tower of the Internet.png)

- Often we draw pictures of machines communicating over the Internet with arrows.  However, the real communication goes through protocol layers and the machine and then is trasported of the network. For College Board and future Computer Knowledge you should become familiar with the following ...

```
    User Machine  <---> Frontend Server <---> Backend Server
    +-----------+         +-----------+         +-----------+
    |  Browser  |         |  GH Page  |         |   Flask   |
    +-----------+    ^    +-----------+    ^    +-----------+
    |    HTTP   |    |    |    HTTP   |    |    |    HTTP   |
    +-----------+    |    +-----------+    |    +-----------+
    |    TCP    |    |    |    TCP    |    |    |    TCP    |   
    +-----------+    |    +-----------+    |    +-----------+
    |     IP    |    V    |     IP    |    V    |     IP    |
    +-----------+         +-----------+         +-----------+
    |  Network  |  <--->  |  Network  |  <--->  |  Network  |
    +-----------+         +-----------+         +-----------+
```

The "http" layer is an application layer protocol in the TCP/IP stack, used for ***communication between web browsers and web servers***. It is the protocol used for transmitting data over the World Wide Web.

The "transport" layer (TCP) is responsible for providing reliable data transfer between applications running on different hosts.  The TCP protocol segments the data into smaller ***chunks called "segments"***. Each segment contains a sequence number that identifies its position in the original stream of data, as well as other control information such as source and destination port numbers, and checksums for error detection.

The "ip" layer is responsible for packetizing data received from the TCP layer of the protocol stack, and then ***encapsulating the data into IP packets***. The IP packets are then sent to the lower layers of the protocol stack for transmission over the network.

The "network" layer is responsible for ***routing data packets between networks*** using the Internet Protocol (IP). This layer handles tasks such as packet addressing and routing, fragmentation and reassembly, and ***network congestion*** control.

#### Previous Big Idea 4 Work

After referencing back to [these notes]({{site.baseurl}}/theinternetnotes/) quite a few times during the process of making this blog, I figured I should link it again to show how comprehensively I've studied this concept in the past.

### Fault Tolerance

> Watch both Daily videos for 4.2

- Complete the network activity, summarize your understanding of fault tolerance.

![Fault Tolerance Diagram]({{site.baseurl}}/images/Screen Shot 2023-04-05 at 3.16.25 PM.png)

Fault tolerance allows systems to complete tasks despite certain connections failing in the process.

Fault tolerance makes systems more reliable but it also requires a lot of resources and time if not balanced carefully. Non-fault-tolerant connections are shown in the black ink, an over-the-top fault tolerant version is in blue, and a balanced set of eight connections is marked in green.

Fault tolerance is also satanic.

#### Video Examples

##### Example 1

![FT Example 1]({{site.baseurl}}/images/Screen Shot 2023-04-15 at 10.03.44 AM.png)

C is the answer. The whole point point of fault tolerance is to allow systems to take advantage of multiple alternate routes to one another, **especially** when other routes are available.

C was the correct answer.

##### Example 2

![FT Example 2]({{site.baseurl}}/images/Screen Shot 2023-04-15 at 10.10.22 AM.png)

A is the answer. A is the only endpoint with only a single route, meaning that another connection (such as to B) would make the system fault tolerant.

A was the correct answer.

### Parallel and Distributed Computing

> Review previous lecture on Parallel Computing and watch Daily vidoe 4.3.  Think of ways to make something in you team project to utilize Cores more effectively.  Here are some thoughts to add to your story of Computers and Networks...

#### Answering Questions

- What is naturally Distributed in Frontend/Backend archeticture?

The frontend/backend structure naturally distributes tasks between frontend and backend, particularly tasks that relate to their differing purposes. Frontend tasks usually relate to user interface or relationship to the backend, while backend tasks can be more computationally taxing and relate to the data needed by the user side.

In the frontend/backend structure, parallel computing is often used to speed up the processing of frontend requests using multiple nodes. A fairly common example is something we already showed in class: image processing is often split across multiple processors.

- Analyze this command in Docker: `ENV GUNICORN_CMD_ARGS="--workers=1 --bind=0.0.0.0:8086"` computing within the server that runs python/gunicorn.  Here is an [article](https://medium.com/building-the-system/gunicorn-3-means-of-concurrency-efbb547674b7)

The `ENV GUNICORN_CMD_ARGS` is setting up to present specific arguments to the gunicorn environment.

The article discusses how `--workers=?` creates `?` workers to handle HTTP requests. the master gunicorn process ensures that the specified number of workers is kept consistent at all times, forking itself initially to create the workers and forking itself again and again as workers crash or fail. In this case, having `1` worker means that only a single forked subprocess is responsible for taking HTTP requests. This is never recommended; the article suggests deciding the amount of workers by doubling your computer's CPU and then adding 1, so in order to optimally end up with only one worker, you'd have to have a CPU of zero, which isn't exactly possible.

The `--bind=?` argument establishes an endpoint for the HTTP processes at the specified address and port. In this case, it uses the default IP host of `0.0.0.0` and the port `8086`, both established locally.

**Other Gunicorn Arguments**

The `--threads:?` argument can be used to provide threads to each of the workers to further divide the process. These threads work in the same memory space as each other, and each worker still has its own unique space in memory.

It is important to understand that the maximum concurrent requests is now represented by the product of `workers * threads`. If one were to provide the argument `--workers:3 --threads:3`, the maximum concurrent processes would be 9. This number should still be defined by twice the CPU plus one. As a result, these settings would be ideal for a quad-core machine (`(4 * 2) + 1 = 9`).

Worker classes can also be used in tandem with Python concurrency libraries. When `threads` are established, the `worker` class is automatically set to `--worker-class=gthread`. When using `gevent`, for example, the `--worker-class=gevent` can be used. This creates broader flexibility for gunicorn concurrency.

> Last week we discussed parallel computing on local machine.  There are many options.  Here is something to get parallel computing work with a tool called Ray.
- Review this [article](https://www.anyscale.com/blog/writing-your-first-distributed-python-application-with-ray)...  Can you get parallel code on images to work more effectively?  I have not tried Ray.

- Code example from ChatGPT using squares.  This might be more interesting if nums we generated to be a lot bigger.

```python
import ray

# define a simple function that takes a number and returns its square
def square(x):
    return x * x

# initialize Ray
ray.init()

# create a remote function that squares a list of numbers in parallel
@ray.remote
def square_list(nums):
    return [square(num) for num in nums]

# define a list of numbers to square
nums = [1, 2, 3, 4, 5]

# split the list into two parts
split_idx = len(nums) // 2
part1, part2 = nums[:split_idx], nums[split_idx:]

# call the remote function in parallel on the two parts
part1_result = square_list.remote(part1)
part2_result = square_list.remote(part2)

# get the results and combine them
result = ray.get(part1_result) + ray.get(part2_result)

# print the result
print(result)
```

**Trying Larger Squares**

We were curious to see how parallel processing would change given larger numbers to square and more of them.

![Larger Numbers]({{site.baseurl}}/images/Screen Shot 2023-04-16 at 12.30.34 PM.png)

This was about a second longer than the `[1, 2, 3, 4, 5]` process above took.

![Even Larger Numbers]({{site.baseurl}}/images/Screen Shot 2023-04-16 at 12.32.47 PM.png)

Adding much larger numbers and a few more, it took almost two more seconds to finish the process.

**Trying More Processes**

I was curious if adding more concurrent processes would make it faster.

![Three Processes]({{site.baseurl}}/images/Screen Shot 2023-04-16 at 12.37.24 PM.png)

I'm somewhat surprised to say that the process took a second less with three concurrent processes than it did with two. I thought this was a pretty interesting test, showing the sort of time save that's possible by creating multiple concurrent processes for even simple things like squaring numbers.