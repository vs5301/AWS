Cloud Computing: On-demand availablity of computer system resources, expecially data storage (cloud storage) and computing power, without direct active management by the user.

Features:
Pay-as-you-go pricing
Provision exactly the right type and size of computing resources you need.
Access as many resources as needed.

Deployment Models of the Cloud:

    Private Cloud:
        Cloud servies used by a single organization, not exposed to the public.
        Complete control.
        Security for sensitive applications.
        Meet specific business needs.

    Public Cloud:
        Cloud resources owned and operated by a third-party cloud service provider delivered over the Internet.
        Six Advantages of Cloud Computing

    Hybrid Cloud:
        Keep some servers on premises and extend some capabilities to the cloud.
        Control sensitive assets in private infrastructure.
        Flexibility and cost-effectiveness of the public cloud.

Five Characteristics of Cloud Computing:

    On-demand self service:
        Users can provision resources and use them without human interaction from the service provider.

    Broad Network Access:
        Resources available over the network, and can be accessed by diverse client platforms.

    Multi-tenancy and resource pooling:
        Multiple customers can share the same infrastructure and application with security and privacy.
        Multiple customers are serviced from the same physical resources.

    Rapid elasticity and scalability:
        Automatically and quickly acquire and dispose resources when needed.
        Quickly and easily scale based on demand.

    Measured Service:
        Usage is measured, users pay correctly for what they have used.

Six Advantages of Cloud Computing:

    Trade capital expense (CAPEX) for operational expenses (OPEX)
        Pay on-demand: don't own hardware
        Reduced Total Cost of Ownership (TCO) & Operational Expenses(OPEX).

    Benefit from massive economies of scale
        Prices are reduces as AWS is more efficient due to large scale

    Stop guessing capacity
        Scale based on actual measured usage.

    Increase speed and agility

    Stop spending money running and maintaining data centers.

    Go global in minutes: leverage the AWS global infrastructure.

Types of Cloud Computing -

    Infrastructure as  Service (IaaS):
        Provide buiding blocks for cloud IT.
        Provides networking, computers, data storage space.
        Highest level of flexibilty.
        Easy parallel with traditional on-premises IT

    Platform as a Service (PaaS):
        Removes the need for your organization to manage the underlying infrastructure.
        Focus on the deployment and management of your application.

    Software as a Service (SaaS):
        Completed pproduct that is run and managed by the service provider.

Choosing an AWS Region:

    Compliance with data government and legal requirements: data never leaves a region without your explicit permission.

    Proximity to customers: reduced latency

    Available services within a Region: new servies and new features aren't available in every region.

    Pricing: pricing varies region to region and is transparent in the service pricing page.

Availablity Zones: One or more discrete data centers with redundant power, networking, and connectivity, that are used to deploy infrastructure.

Fundamentals of AWS Cloud: Compute, Storage, and Data transfer out of the AWS Cloud.

Shared Responsibility Model (Diagram):

    Customer = responsibility for the security IN the cloud.

    AWS = responsibility for the security OF the cloud

IAM: Identity and Access Management

    Global service
    Example: Root AWS account  created by default, shouldn't be used or shared.
    Users are people within the organisation, and can be grouped.
    Groups only contain users, not other groups.
    Users don't have to belong to a group, and user can belong to multiple groups.

IAM: Permissions

    Users or Groups can be assigned JSON documents called policies.
    These policies define the permissions of the users.
    In AWS you apply the least-privilege principle: don't give more permissions than a user needs.

IAM Policies Structure:

    Consists of
        Version: Policy language version, always include "2012-10-17"
        Id: an identifier for the policy (optional).
        Statement: one or more individual statements (required).

    Statement consists of
        Sid: an identifier for the statement (optional)
        Effect: whether the statement allows or denies access (Allow, Deny).
        Principal: account/user/role to which this policy applied to.
        Action: list of actions this policy allows or denies.
        Resource: list of rescources to which the acitons applied to
        Condition: conditions for when this policy is in effect (optional).

IAM - Password Policy

    Strong passwords = higher security
        Set a minimum password length
        Require specific character types:
            including uppercase letters
            lowercase letters
            numbers
            non-alphanumeric characters
        Allow all IAM users to change their own passwords
        Require users to change their password after some time (password expiration)
        Prevent password re-use

Multi Factor Authentication

    MFA = password + security device

    Benefits:
        If password is stolen or hacked, account is not compromised.

    MFA devices options in AWS

        Virtual MFA device: Support for multiple tokens on a single device.
            Google Authnticator (phone only)
            Authy (multi-device)

        Universal 2nd Factor Security Key: Support for multiple root and IAM users using a single security key.
            YubiKey by Yubico (3rd party)

        Hardware Key Fob MFA Device
            Provided by Gemalto (3rd party)

        Hardware Key Fob MFA Device for AWS GovCloud (US)
            Provided by SurePassID (3rd party)

Three options to access AWS:
AWS Management Console (protected by password + MFA)
AWS Command Line Interface (CLI): protected by access keys
AWS Software Developer Kit (SDK): for code: protected by access keys

Access Keys are secret
Access Key ID ~= username
Secret Access Key ~= password

AWS CLI: tool that enables you to interact with AWS services using command in your command-line shell. Direct access to public APIs of AWS.

AWS SDK: Language-specific APIs (set of libraries). Enables you to access and manage AWS services programmatically and is embedded within your application.
Eg: AWS Cli

IAM Roles: An IAM entity that defines a set of permissions for making AWS service requests, that will be used by AWS services.
Some AWS service will need to perform actions on your behalf. To do so, we will assign permission to AWS services with IAM Roles.
Common roles:
EC2 Instance Roles
Lambda Function Roles
Roles for CloudFormation

IAM Security Tools

    IAM Credentials Report (account-level)
        a report that lists all your account's users and sthe status of the credentials

    IAM Access Advisor (user-level)
        Access advisor shows the servies permission granted to a user and when those services were last accessed.
        This information can be used to revise policies.

IAM Policies: An entity that when attached to an identity or resource, defines their permissions.

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
