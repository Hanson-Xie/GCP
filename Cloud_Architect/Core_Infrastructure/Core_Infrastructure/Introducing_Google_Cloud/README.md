# Introducing Google Cloud

## What is cloud computing?
It has 5 belowing traits:
1. customers get computing resources that are on-demand and self-service.
2. customers get access to those resources over the Internet from anywhere they have a connection.
3. the cloud provider has a big pool of those resources and allocates them to users out of that pool. (That allows provider has a big pool of those resources and allocates them to users out of that pool)
4. the resources are elastic, which means they're flexible, so customers can be. If customers need more resources, they can get more and quickly.
5. customers pay only for what they use or reserve as they go

## Two new types of offerings for virtualized data centers customers
1. Iaas (Infrastructure as a service)
(1) Provides: raw compute,storage and network capabilities.
(2) Customers Pay for: the resources they allocate ahead of time
2. Paas (Platform as a service)
(1) bind code to libraries that provide access to the infrastructure that the application needs. This allows more resources to be focused on application logic.
(2) Customers Pay for the resources they actually use

## The Google Cloud Network
1. App location affects:
(1) Availability
(2) Durability
(3) Latency

## Security
1. Hardware infrastructure layer
(1) Hardware design and provenance
(2) Secure boot stack
(3) Premises security
2.Service deployment layer
(1)Encryption of inter-service communication
3.User identity layer
4.Storage services layer
5.Internet communication layer
(1)Google Front End
(2)Denial of Service protection
6.Operational security layer
(1)Itrusion detection
(2)Reducing insider risk
(3)Employee Universal Second Factor use
(4)Software development practices

# Resources and access in the cloud

## TheGoogle Cloud resource hierarchy
### How policies are managed and applied when you use Google Cloud
#### Inherited downward
(1)Organization node
(2)Folder
(3)Project
(4)Resources

## IAM (Identity and Access Management)
### With IAM, the administrators can apply policies that define who can do what on which resources.

1.Who
(1)A Google account
(2)A Google group
(3)A Service account
(4)A Cloud Identity Domain

2.What
(1)Defined by a role
(2)Roles:
    a. Basic
    b. Predefined
        With Compute Engine, you can apply specific Predefined roles such as Instance Admin to Compute Engine resources in a given project, a given folder, or an entire organization. 
    c. Custom
    you'll need to manage the permissions that define the Custom role you've created, because of this, some organizations decide they'd rather use the Predefined roles. Second, Custom roles can only be applied to either the project level or organization level. They can't be applied to the folder level.

3.Which

## Service Account
### You want to give permissions to a Compute Engine Virtual Machine rather than to a person

## Interacting with Google Cloud

1. The Cloud Console
    Web-based GUI
2. The Cloud SDK in cloud shell
    command line
3. API
4. The Cloud Console Mobile App 

# Virtual Machine and Networks in the Cloud

## VPC

1. Definition: VPC is a secure individual private cloud computing model hosted within a public cloud, like Google Cloud.
2. VPC networks connect Google Cloud resources to each other and to the internet. This includes segmenting networks.
3.Google VPC networks are global. They can also have subnets, which is a segmented piece of the larger network in any Google loud region worldwide.

## Compute Engine
### Google Cloud’s IaaS solution: Compute Engine. 

1. for each VM that runs for more than 25% of a month, Compute Engine automatically applies a discount for every additional minute. Compute Engine also offers committed-use discounts.

2. Preemptible and Spot VMs.
(1) you have a workload that doesn’t require a human to sit and wait for it to finish–such as a batch job analyzing a large dataset. You can save money, in some cases up to 90%, by choosing Preemptible or Spot VMs to run the job.
(2) Compute Engine has permission to terminate a job if its resources are needed elsewhere. Although savings are possible with preemptible or spot VMs, you'll need to ensure that your job can be stopped and restarted. 

## Important VPC compatibilities

1. VPCs have routing tables. VPC routing tables are built-in so you don’t have to provision or manage a router.
2.Another thing you don’t have to provision or manage for Google Cloud is a firewall.
3.VPC peering : when you have serveral projects and require the VMs to connect with each other

## Cloud Load Balancing

1. The job of a load balancer is to distribute user traffic across multiple instances of an application.
2. VPC offers a suite of load-balancing options:
(1)Global HTTP(S) load balancing:If you need cross-regional load balancing for a web application
(2)Global SSL Proxy load balancer: For Secure Sockets Layer traffic that is not HTTP
(3)Global TCP Proxy load balancer: if it’s other TCP traffic that doesn’t use SSL
(4)The last 2:
    Only work for specific port numbers, and they only work for TCP.
    a.Regional load balancer: If you want to load balance UDP traffic, or traffic on any port number
    b.Regional internal:  if you want to load balance traffic inside your project, say, between the presentation layer and the business layer of your application

## Cloud DNS and Cloud CDN

1.DNS is what translates Internet host names to addresses.
2.Edge caching refers to the use of caching servers to store content closer to end users. 

## Connecting networks to Google VPC
1.IPsec VPN protocol:
start with a virtual private network connection over the Internet and use the IPsec VPN protocol to create a tunnel connection.
(1)Cloud router lets other networks and google VPC exchange route information over the VPN using the border gateway protocol.
(2)if you add a new sub net to your google VPC, your on premises network will automatically get roots to it.
(3)But using the internet to connect networks isn't always the best option for everyone, either because of security concerns, or because of bandwidth reliability.

2. Peering ways:
Peering means putting a router in the same public data center as a google point of presence, and using it to exchange traffic between networks. 

(1)Direct Peering
(2)Carrier Perring
    a.Customers who aren't already in a point of presence, can work with a partner in the carrier peering program to get connected.
    b.Carrier peering gives you direct access from your on premises network, through a service provider's network to google workspace and to google cloud products that can be exposed through one or more public IP addresses.
(3)Downside:peering though is that it isn't covered by a Google service level agreement.

3.Dedicated Interconnect
(1) Timing : If getting the highest up times for interconnection is important
(2) allows for one or more direct private connections to Google. If these connections have to apologies that meet Google specifications, they can also be covered by an SLA of up to 99.99 percent
(3)these connections can be backed up by a VPN for even greater reliability.

4.Partner Interconnect
which provides connectivity between an on premises network and a VPC network for a supported service provider.

(1) Timing :
    a.A Partner Interconnect connection is useful if a data center is in a physical location that can't reach a Dedicated Interconnect co location facility.
    b. if the data needs don't warrant an entire 10 GigaBytes per second connection depending on availability, needs.
(2)Partner Interconnect can be configured to support mission critical services or applications that can tolerate some downtime.
(3)Google isn't responsible for any aspects of Partner Interconnect provided by the third party service provider nor any issues outside of Google's network

# Google Cloud storage options

1. Cloud Storage
Timing: Consider using Cloud Storage if you need to store immutable blobs larger than 10 megabytes

(1) a service that offers developers and IT organizations durable and highly available object storage
    a.Object storage is a computer data storage architecture that manages data as “objects” and not as a file and folder hierarchy (file storage), or as chunks of a disk (block storage).
(2)These unique keys are in the form of URLs, which means object storage interacts well with web technologies.
(3)Cloud Storage’s primary use is whenever binary large-object storage (also known as a “BLOB”) is needed for online content such as videos and photos, for backup and archived data and for storage of intermediate results in processing workflows.
(4)Cloud Storage files are organized into buckets.
(5)Enale "versioning":
    Cloud Storage will keep a detailed history of modifications -- that is, overwrites or deletes -- of all objects contained in that bucket.
(6)Accessment: For most purposes, IAM is sufficient. Roles are inherited from project to bucket to object. If you need finer control, you can create access control lists. Each access control list consists of two pieces of information. 

2. Cloud SQL
if you need full SQL support for an online transaction processing system
(1)Timing: Is designed to hand off mundane but necessary and often time-consuming tasks to Google,Cloud SQL is best for web frameworks and existing applications, like storing user credentials and customer orders.
(2)Provides:
    a.MySQL
    b.PostgreSQL
    c.SQL Server 
(3)Cloud SQL doesn't require any software installation or maintenance
(4)A benefit of Cloud SQL instances is that they're accessible by other google Cloud services and even external services

3.Cloud Spanner
if you need full SQL support for an online transaction processing system or you need horizontal scalability, not just through read replicas, consider using Cloud Spanner.
(1)Cloud Spanner is a fully managed relational database service that Cloud Spanner is a fully managed relational database service that scales horizontally, is strongly consistent, and speaks SQL.
(2)Timing:
    a.A SQL relational database management system with joins and secondary indexes Built-in high availability Strong global consistency
    b. high numbers of input and output operations per second

4.Fire Store
Consider Firestore if you need massive scaling and predictability together with real time query results and offline query support,Firestore is best for storing, syncing, and querying data for mobile and web apps
Firestore is a flexible, horizontally scalable, NoSQL cloud database for mobile, web, and server development. 
(1)Performance:Queries can include multiple, chained filters and combine filtering and sorting options. They're also indexed by default, so query performance is proportional to the size of the result set, not the dataset.
(2)Timing:
    a.Firestore uses data synchronization to update data on any connected device.
    b.it's also designed to make simple, one-time fetch queries efficiently.
(3)Pricing Perspective:
    a.you’re charged for each document read, write, and delete that you perform with Firestore. Queries are also charged at the rate of one “document read” per query, whether the query returns data or not.
    b.for the amount of storage your data consumes and for certain kinds of network bandwidth used to access your data

5.Cloud Bigtable
consider using Cloud Bigtable if you need to store a large number of structured objects, Bigtable is best for analytical data with heavy read and write events
Cloud Bigtable is Google's NoSQL Big data database service.
(1) Timing: if they're working with more than one terabyte of semi-structured or structured data.  transactions where strong relational semantics are not required.

# Containers In The Cloud
### The idea of a container is to give the independent scalability of workloads in PaaS and an abstraction layer of the OS and hardware in IaaS. 
### A configurable system lets you install your favorite runtime, web server, database, or middleware, configure the underlying system resources, such as disk space, disk I/O, or networking, and build as you like.
### The smallest unit of compute is an app with its VM.
### In essence, the OS is being virtualized. It scales like PaaS but gives you nearly the same flexibility as IaaS.


1. App Engine:
(1) use for: you get access to programming services, so you only need to write your code in self-contained workloads that use these services and include any dependent libraries.

(2)Environment
    a.Stnadard
         for people who want the service to take maximum control of their web and mobile applications deployment and scaling. 
         
        I.based on container instances running on Google's infrastructure.
        II.Containers are pre-configured with a runtime from a standardized list of supported languages and versions, which includes libraries that support App Engine standard APIs
        III.Process
            i.First, a web application is developed and tested locally.
            ii.Second, the SDK is used to deploy the application to App Engine. 
            iii.Third, App Engine scales and services the application. App Engine also offers a flexible environment.
        IV: Pros:
            Fast.It starts up instances of your application in seconds
        V: Cons:
            But the standard environment, you can't use SSH to connect to the virtual machines on which your application runs and you can't write to a local disk. 
            , but you have less access to the infrastructure in which your application runs.
        VI:Pricing:
        after a free tier usage, you pay per instance class with automatic shutdown.

    b.Flexible
        Google Kubernetes Engine, however, gives the application owner the full flexibility of Kubernetes, App Engine's flexible environment is somewhere between the two.
        I.App Engine flexible allows users to also benefit from custom configurations and libraries while still keeping their main focus on what they do best, writing code. 
        II.Pricing: pay for resource allocation per hour with no automatic shutdown.


2. Kubernets
Update Strategy
Kubernetes is an open source platform for managing containerized workloads and services.
It makes it easy to orchestrate many containers on many hosts, scale them as microservices and easily deploy rollouts and rollbacks. At the highest level Kubernetes is a set of APIs that you can use to deploy containers on a set of nodes called a cluster.

(1) In Kubernetes, a node represents a computing instance like a machine. Note that this is different to a node on google cloud, which is a virtual machine running in compute engine.
    a. You can describe a set of applications and how they should interact with each other, and Kubernetes determines how to make that happen.
    b.Deploying containers on nodes by using a wrapper around one or more containers is what defines a Pod.

(2)Pods:A Pod is the smallest unit in Kubernetes that you can create or deploy. It represents a running process on your cluster as either a component of replication or an entire app.

(3)Kubernetes creates a service with a fixed IP address for your pods, and a controller says I need to attach an external load balancer with a public IP address to that service so others outside the cluster can access it. In GKE, the load balance is created as a network load balancer.

(4)Any client that reaches that IP address will be routed to a pod behind the service.

(5)But the real strength of Kubernetes comes when you work in a declarative way.

## Hybrid and multi-cloud
 It allows you to keep parts of your system's infrastructure on-premises while moving other parts of the cloud. 

### Anthos
#### Anthos is a hybrid and multi cloud solution powered by the latest innovations in distributed systems and service management software from Google.

## Google Cloud API management tools
1.Cloud Endpoints
Cloud Endpoints is a distributed API management system that uses a distributed Extensible Service Proxy, which is a service proxy that runs in its own Docker container.
The goal is to help you create and maintain even the most demanding APIs with low latency and high performance. 
2.API Gateway
API Gateway enables you to provide secure access to your backend services through a well-defined REST API that is consistent across all of your services, regardless of the service implementation.
3.Apigee Edge.
Apigee Edge has a specific focus on business problems, like rate limiting, quotas, and analytics.
This allows them to stand up microservices to implement each in turn until the legacy application can finally been retired

## Cloud Run
It's built on Knative, an open API and runtime environment built on Kubernetes that gives you freedom to move your workloads across different environments and platforms. 
The pricing model on Cloud Run is unique as you only pay for the system resources you use while a container is handling web requests with a granularity of 100 milliseconds and when it's starting or shutting down.
You don't pay for anything if your container doesn't handle requests.


# Development and Deployment in the cloud

1.Developemnt
(1)Cloud Source Repositories
    provides full-featured Git repositories hosted on Google Cloud that support the collaborative development of any application or service, including those that run on App Engine and Compute Engine.
(2)Cloud Functions
a lightweight, event-based, asynchronous compute solution that allows you to create small, single-purpose functions that respond to cloud events, without the need to manage a server or a runtime environment.
    a.Pricing
    You’re billed to the nearest 100 milliseconds, but only while your code is running. 
2. Deployment
-Terraform
Terraform then uses that template to determine the actions needed to create the environment your template describes

# Logging and Monitoring in the Cloud

1. Monitoring
Collecting, processing, aggregating, and displaying real-time quantitative data about a system, such as query counts and types, error counts and types, processing times, and server lifetimes.

2.Measuring performance and reliability
(1)Latency
Latency measures how long it takes a particular part of a system to return a result. 
    a.page load latency, number of requests waiting for a thread, query duration, service response time, transaction duration, time to first response, and time to complete data return.
(2)Traffic
measures how many requests are reaching your system
    a.the number of HTTP requests per second, number of requests for static versus dynamic content, network IO, number of concurrent sessions, number of transactions per second, number of retrievals per second, number of active requests, number of write operations, number of read operations, and number of active connections.

(3)Saturation
measures how close to capacity a system is. It's important to note though, that capacity is often a subjective measure that depends on the underlying service or application.
    a.percent memory utilization, percent thread pool utilization, percent cache utilization, percent disk utilization, percent CPU utilization, disk quota, memory quota, number of available connections, and number of users on the system.

(4)Errors
which are events that measure system failures or other issues.
    a.wrong answers or incorrect content, the number of 400 and 500 HTTP codes, the number of failed requests, the number of exceptions, the number of stack traces, servers that fail liveness checks, and the number of dropped connections.

3.Understanding SLIs, SLOs, and SLAs
(1)Service level indicators (SLI)
are carefully selected monitoring metrics that measure one aspect of a services reliability.
    a.Ideally, SLI should have a close linear relationship with your users experience of that reliability. 
    b.the number of good events divided by the count of all valid events.
(2)A service level objective, or SLO
combines a service level indicator with a target reliability.

    a.An SLI must be a number or a Delta, something we can measure in place in a mathematical equation. SLO goals must be achievable.
(3)service-level agreements or SLAs,
are commitments made to your customers that your systems and applications will only have a certain amount of downtime. 

4.Integrated observability tools






