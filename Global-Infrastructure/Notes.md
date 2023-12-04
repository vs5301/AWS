Global Application - an application deployed in multiple geographies, (regions or edge locations)

Decreased Latency
Latency is the time it takes for a network packet to reach a server
Takes time for a packet from Asia to reach US
Deploy applications closer to your users to decrease latency, better experience

Disaster Recovery
If an AWS region goes down due to natural disasters
Can fail-over to another region and have application still working
DR plan is important to increase the availability of your application

Attack protection: distributed global infrastructure is harder to attack

Regions: For deploying applications and infrastructure
Availability Zones: Made of multiple data centers
Edge Locations (Points of Presence): for content delivery as close as possible to users

Global Applications in AWS

    Global DNS: Route 53
        Greate to route users to the closest deployment with least latency
        Great for disaster recovery strategies
    Global Content Delivery Network (CDN): CloudFront
        Replicate part of your application to AWS Edge Locations - decrease latency
        Cache common requests - improved user experience and decreased latency
    S3 Transfer Acceleration
        Accelerate global uploads & downloads into Amazon S3
    AWS Global Accelerator
        Improve global applicaiton availability and performance using the AWS global network

Amazon Route 53

    Route53 is a Managed DNS
    DNS is a collection of rules and records which helps clients understand how to reach server through URLs

Route 53 Routing Policies

    Simple Routing Policy - no health checks
    Weighted Routing Policy - able to use health checks
    Latency Routing Policy - users are connected to closest servers
    Failover Routing Policy - Disaster recovery - health check on primary

AWS CloudFront

    Content Delivery Network (CDN)
    Improves read performance, content is cached at the edge
    Improves users experience
    216 Point of Presence globally (edge locations)
    DDoS protection, integration with Shield, AWS Web Application Firewall

CloudFront - Origins

    S3 Bucket
        For distributing files and caching them at the edge
        Enchanced security with CloudFront Origin Access Control (OAC)
        OAC is replacing Origin Access Identity (OAI)
        CloudFront can be used as an ingress (to upload files to S3)

    Custom Origin (HTTP)
        Application Load Balancer
        EC2 instance
        S3 website (must first enable the bucket as a static S3 website)
        Any HTTP backend chosen

CloudFront vs S3 Cross Region Replication

    CloudFront:
        Global Edge network
        Files are cached for a TTL (maybe a day)
        Great for static content that must be available everywhere

    S3 Cross Region Replication
        Must be setup for each region you want replication to happen
        Files are updated in near real-time
        Read only
        Great for dynamic content that needs to be available at low-latency in few regions

S3 Transfer Acceleration

    Increase transfer speed by transferring file to an AWS edge location which will forward the data to the S3 bucket in the target region

AWS Global Accelerator

    Improve global application availablity and performance using the AWS global network
    Leverage the AWS internal network to optimize the route to application (60% improvement)
    Two Anycast IP are created for application and traffic is sent through Edge Locations
    Edge Locations send the traffic to your application

AWS Global Accelerator vs CloudFront

    Both use the AWS global network and its edge locations around the world
    Both services integrate with AWS Shield for DDoS protection
    CloudFront - CDN
        Improves performance for your cacheable content (such as images and videos)
        Content is served at the edge
    Global Accelerator
        No caching, proxying packets at the edge to applications running in one or more AWS Regions
        Improves performance for a wide range of applications over TCP or UDP
        Good for HTTP use cases that require static IP addresses
        Good for HTTP use cases that required deterministic, fast regional failover

AWS Outposts

    Hybrid Cloud - businesses that keep an on-premises infrastructure alongside a cloud infrastructure
    Two ways of dealing with IT systems:
        AWS cloud (using the AWS console, CLI & APIs)
        One for on-premises infrastructure

    AWS Outposts are "server racks" that offers same AWS infrastructure, services, APIs & tools to build own applications on-premises just as in cloud

    AWS will setup and manage "Outpost Racks" within on-premises infrastructure and start leveraging AWS services on-premises

    Benefits
        Low latency access to on-premises systems
        Local data processing
        Data residency
        Easier migration from on-premises to the cloud
        Fully managed service

AWS Wavelength

    Infrastructure deployments, embedded within the telecommuications providers datacenters at the edge of the 5G networks
    Brins AWS services to the edge of the 5G networks
    Ultra-low latency applications through 5G networks
    Traffic doesn't leave the Communication Service Provider's (CSP) network
    High-bandwidth and secure connection to the parent AWS Region
    No additional charges or service agreements
    Use cases: smart cities, ML-assisted diagnostics, connected vehicles, interactive live video streams, AR/VR, real-time gaming

AWS Local Zones

    Places AWS compute, storage, database, and other selected AWS services closer to end users to run latency-sensitive applications
    Extend your VPC to more locations - "Extension of an AWS Region"
    Compatible with EC2, RDS, ECS, EBS, ElastiCache, Direct Connect ...
