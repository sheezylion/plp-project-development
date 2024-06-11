# Load Balancer Concepts and Differences between L4 and L7 Load Balancers

## What is load balancing?

Load balancing is a technique used to distribute network traffic across a pool of servers known as a server farm. It optimizes network performance, reliability and capacity, reducing latency as the demand is equally distributed among multiple servers and compute resources.

Load balancing uses an appliance -- either physical or virtual – to identify in real time which server in a pool can best meet a given client request, while ensuring heavy network traffic doesn't unduly overwhelm a single server.

In addition to maximizing network capacity and ensuring high performance, load balancing provides failover. If one server fails, a load balancer immediately redirects its workloads to a backup server, thus mitigating the effect on end users.

### How load balancing works

Load balancers handle incoming requests from users for information and other services. They sit between the servers that handle those requests and the internet. Once a request is received, the load balancer first determines which server in a pool is available and online and then routes the request to that server. During times of heavy loads, a load balancer acts promptly and can dynamically add servers in response to spikes in traffic. Conversely, load balancers can drop servers if demand is low.

<img src="images/how-does-load-balancing-work.png">

### Types of load balancers

Load balancing is a key component of highly available infrastructures. Depending on a network's needs, various types of load balancers can be deployed with different storage capabilities, functionalities and complexities.

A load balancer can be a physical appliance, a software instance or a combination of both. The following are two types of load balancers:

<b>Hardware load balancer</b>

A hardware load balancer is a hardware device with specialized and proprietary built-in software that's designed to handle massive amounts of application traffic. These load balancers have a built-in virtualization capability and enable multiple instances of a virtual load balancer to be used on a single device.

Traditionally, vendors loaded proprietary software onto dedicated hardware and sold it to users as standalone appliances -- usually in pairs to provide failover if one system goes down. Growing networks require an organization to purchase additional or larger appliances.

<b>Software load balancer</b>

Software load balancing runs on virtual machines (VMs) or white box servers, most likely as an application delivery controller (ADC) function. ADCs typically offer additional features, including caching, compression and traffic shaping. Popular in cloud environments, virtual load balancing can offer a high degree of flexibility. For example, it enables users to automatically scale up or down to mirror traffic spikes or decreased network activity.

### Cloud-based load balancing

Cloud load balancing uses the cloud as its underlying infrastructure to balance cloud computing environments.

The following are examples of cloud-based load-balancing models:

Network load balancing.

This is the fastest load-balancing option available. It operates on Layer 4 of the OSI model and uses network layer information to transport network traffic.

HTTP Secure load balancing.

This enables network administrators to distribute traffic based on information coming from the HTTP address. It's based on Layer 7 and is one of the most flexible load-balancing options.

Internal load balancing.

This is similar to network load balancing, but it can also balance traffic distribution across the internal infrastructure.

### Differences between L4 and L7 Load Balancers

Load balancing is usually categorized as supporting either Layer 4 or Layer 7 of the Open Systems Interconnection (OSI) communication model. Layer 4 load balancers distribute traffic based on transport data, such as IP addresses and TCP port numbers. Layer 7 load-balancing devices make routing decisions based on application-level characteristics, which include Hypertext Transfer Protocol (HTTP) header information and the actual contents of the message, such as URLs and cookies. Layer 7 load balancers are more common, but Layer 4 load balancers remain popular, particularly in edge deployments.
