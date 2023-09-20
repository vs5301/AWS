Amazon EC2

    EC2 = Elastic Compute Cloud = Infrastructure as a Service
    It mainly consists in the capability of:
        Renting virtual machines (EC2)
        Storing data on virtual drives (EBS)
        Distributing load across machines (ELB)
        Scaling the services using an auto-scaling group (ASG)

EC2 sizing and configuration options

    Operating System: Linux, Windows or Mac OS
    How much compute power & cores (CPU)
    How much random-access memory (RAM)
    How much storage space:
        Network-attached (EBS & EFS)
        hardware (EC2 Instance Store)
    Network card: speed of the card, Public IP address
    Firewall rules: security group
    Bootstrap script (configure at first launch): EC2 USer Data

It is possible to bootstrap our instances using an EC2 User data script.
Bootstrapping means launching commands when a machine starts.

EC2 Instance Types -

    General Purpose
        General purpose instances provide a balance of compute, memory and networking resouces, and can be used for a variety of diverse workloads. These instances are ideal for applications that use their resources in equal proportions such as web servers and code repositories.

        Great for a diversity of workloads such as web servers or code repositories.
        Balance between:
            Compute
            Memory
            Networking

    Compute Optimised
        Compute Optimized instances are ideal for compute bound applications that benefit from high performance processors. Instance belonging to this family are well suited for batch processing workloads, media transcoding, high performance web servers, high performace computing (HPC), scientific modeling, dedicated gaming servers ad server engine, machine learning inference and other compute intensive applications

        Great for compute-intensive tasks that require high performance processors:
            Batch processing workloads
            Media transcoding
            High perforamnce web servers
            High performace computing (HPC)
            Scientific modeling & machine learning
            Dedicated gaming servers

    Memory Optimised
        Memory optimized instances are designed to deliver fast performance for workloads that process large data sets in memory

        Use cases:
            High preformance, relational/non-relational databases.
            Distributed web scale cache stores
            In-memory databases optimized for BI (Business Intelligence)
            Applications performaing real-time processing or unstructured data.

    Storage Optimized
        Storage optimized instances are designed for workloads that require high, sequential read and write access to very large data sets on local storage. They are optimized to deliver tens of thousnads of low-latency, random I/O operations per second (IOPS) to applications.

        Use cases:
            High frequency online transaction processing (OLTP) systems
            Relational & NoSQL databsases
            Cache for in-memory databses (eg, Redis)
            Data warehousing applications
            Distributed file systems

Security Groups
Control how traffic is allowed into or out of our EC2 Instances. Only contain allow rules. Security groups can reference by IP or by security group.

        Can be attached to multiple instances.
        Locked down to a region/VPC combination.
        Does live "outside" the EC2 - if traffic is blocked the EC2 instance won't see it.
        Good to maintain one separate security group for SSH access.
        All inbound traffic is blocked by default.
        All outbound traffic is authorised by default.

EC2 Purchasing Options

    EC2 On Demand
        Pay for what you use.
        Has highest cost but no upfront payment
        No long-term commitment
        Recommended for short-term and un-interrupted workloads, where you cannot predict how application will behave.

    EC2 Reserved Instances
        Up to 72% disount compared to on-demand.
        Reserve a specific instance attribute (Instance type, region, tenancy, OS)
        Reservation Period - 1 year (+discount ) or 3 years (+++discount)
        Payment options - No upfront (+), Partial Upfront(++), All upfront(+++)
        Reserved Instance's Scopt - Regional or Zonal (reserve capacity in an AZ)
        Recommended for steady-state usage applications
        Can buy and sell in the reserved instance marketplace.
        Convertible Reserved Instance
            Can change the EC2 instance type, instance family, OS, scope and tenancy.
            Up to 66% discount

    EC2 Savings Plans
        Get a discount based on long-term usage (up to72% - same as RIs)
        Commit to a certain type of usage ($10/hour for 1 or 3 years)
        Usage beyond EC2 Savings Plans is billed at the On-Demand price.
        Locked to a specific instance family & AWS region
        Flexible across
            Instance Size
            OS
            Tenancy

    EC2 Spot Instances
        Can get a discount of up to 90% compared to On-demand
        Instances that you can "lose" at any point of time if your max price is less than the current spot price
        The MOST cost-efficient instances in AWS
        Useful for workloads that are resilient to failure
            Batch jobs
            Data analysis
            Image processing
            Any distributed workloads
            Workloads with a flexible start and end time
        Not suitable for critical jobs or databases

    EC2 Dedicated Hosts
        A physical server with EC2 instance capacity fully dedicated to your use.
        Allows you address compliance requirements and use your existing server-bound software licenses (per-socket, per-core, pe-VM software licenses)
        Purchsing Options:
            On-demand - pay/s for active Dedicated host
            Reserved - 1 or 3 years (No Upfront, Partial Upfront, All Upfront)
        Most expensive option
        Useful for software that have complicated license model.
        Or for the companies that have strong regulatory or compliance needs.

    EC2 Dedicated Instances
        Instances run on hardware that's dedicated to you
        May share hardware with other instances in same account
        No control over instance placement (can/move hardware after Stop/Start)

    EC2 Capacity Reservations
        Reserve On-Demand instances capacity in a specific AZ for any duration
        You always have access to EC2 capacity when you need it
        No time commitment (create/cancel anytime), no billing discounts
        Combine with Regional Reserved Instances and Savings Plans to benefit from billing discounts
        You're charged at On-Demand rate whether you run instances or not.
        Suitable for short-term, uninterrupted workloads that needs to be in a specific AZ.

Shared Responsibility Model for EC2

    AWS
        Infrastructure (global network security)
        Isolation on physical hosts
        Replacing faulty hardware
        Compliance validation

    User
        Security Group rules
        Operating-system patches and updates
        Software and utilities installed on the EC2 instance
        IAM Roles assigned to EC2 & IAM user access management.
        Data Security on your instance
