# File (NAS) vs. Block (SAN) vs. Object Cloud Storage

When considering how to build out your storage architecture, you need to consider both cost and performance, but most importantly, you need to know what type of enterprise storage to use to house your data. Enterprise storage systems are divided into three categories today: SAN, NAS, and Object. Like most storage systems, each has both advantages and disadvantages. So how do you know which one is right for you?

## What is storage? Why we need storage?

Storage is the collection of methods and technologies that can capture and hold digital information on media. Storage is normally described as the data storage devices that are connected to the computer through input or output operations that includes flash devices, hard disks, SAN, NAS, old tape systems and other different types of medium.

Storage network protocols enable applications, servers and other systems to interface with storage across a network. They also make it possible for users to share files and for organizations to support greater storage capacities than can be easily achieved with direct-attached storage.

### What is SAN?

Storage area network storage, otherwise known as SAN, or block storage, refers to block-based storage accessible over a network. SAN uses the same abstraction as a hard drive where blocks of data can be read or written at a specific location, which is why it’s called block-based storage. Most applications require a file system on top to organize the data stored on the block storage. The exceptions are a few databases and virtual machines that directly consume block storage. Unlike direct-attached storage (DAS), a SAN is accessed over the network. The protocols used are Fibre Channel, iSCSI e.g., over Ethernet, or NVMe over fabric.

The major downside of SAN is that you need a file system on top that needs to be exported to storage consumers. Needing a file system on top really sounds like something Monty Python’s “Royal Society for Putting Things on Top of Other Things” would do. All jokes aside, when one or multiple head nodes export the file system it often introduces a significant performance bottleneck, e.g., when exporting the file system via NFS.

#### Advantages of SAN

- It has economies of scale similar to that of NAS
- It has higher hardware utilization, similar to that of NAS
- It has speed similar or comparable to DAS
- It allows virtual environments, cloud computing, etc.

#### Disadvantages of SAN

- Its performance is affected by other SAN users
- Its performance is limited by network if configured incorrectly
- It requires multiple static IP Addresses
- It generally consumes more IP addresses than NAS devices

### What is NAS?

NAS stands for network-attached storage, but in actuality, it’s a file system storage that is accessed over a network. The significant advantage of NAS storage is that applications and users can directly use the file system. There’s no extra layer needed. However, the term NAS doesn’t say anything about the storage architecture behind the file system that you see.

For example, a simple Linux server exporting local storage via NFS is considered NAS. However, this kind of NAS storage is monolithic, can only be scaled up (i.e., add more drives into a single box), and doesn’t offer a lot of fault tolerance. SOHO (small office home office) NAS boxes or so-called filers (monolithic enterprise NAS appliances) are other examples of this. In contrast, a scale-out NAS system has an architecture where you can add more servers or boxes to increase capacity, and ideally, also performance.

#### Advantages of NAS

- It is the economical way to provide large storage to many persons or computers
- It is several times easier to setup and configure versus SAN
- It is easier way to provide RAID redundancy to mass amount of users
- It allows users permissions, folder privileges, restricted access to documents, etc
- It has higher utilization of storage resources

#### Disadvantages of NAS

- It requires IP Address and takes up network space
- It has slower latency and potentially maximum data-transfer issues
- It performance can be affected by network status

### Object Storage?

Object storage, also known as object-based storage, is the last category of enterprise storage. It is a data storage strategy that sections data into distinct units or objects and stores them in isolated buckets with all relevant metadata and a custom identifier. Object storage has a flat namespace, as opposed to file systems, or a NAS, which have a hierarchical folder structure. Since Amazon invented it to provide cost-effective storage for large amounts of data, the Amazon product name S3 is used synonymously with the term object storage.

There are two main differences between object storage and both SAN and NAS. The first difference is consistency. Both SAN and NAS provide strong consistency, so when you write to a file or block, you have the guarantee that the next read will return the latest data you wrote to the file or block. This consistency model is very intuitive, and most applications rely on it. On the other hand, object storage has very relaxed consistency guarantees (also called eventual consistency), which in reality means that you have no guarantees. Your read might return any value previously written to the object, so applications have to be able to cope with this; therefore, object storage is mainly used for write-once data or archival only. You can find out more about the differences between file and object here.

The second major difference is protocol. Object storage is accessed via the HTTP protocol – the same protocol your web browser uses to request the page you are reading right now. This makes it easy to access object storage from a variety of applications. However, HTTP was never designed for speed or efficiency, whereas SAN and NAS protocols are all about performance.
