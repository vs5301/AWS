Amazon S3 Use cases

    Backup and storage
    Disaster Recovery
    Archive
    Hybrid Cloud storage
    Application Hosting
    Media hosting
    Data lakes and big data analytics
    Software delivery
    Static website

Amazon S3 - Buckets

    Amazon S3 allows people to store objects (files) in 'buckets' (directories)
    Buckets must have a globally unique name, across all regions, all accounts
    Buckets are defined at the region level
    S3 looks like a global service but buckets are created in a region
    Naming Convention
        No uppercase, underscore
        3 - 63 characters
        Not an IP
        Must start with lowercase letter or number
        Must not start with prefix xn-- and must end with suffix -s3alias

Amazon S3 - Objects

    Objects (files) have a key
    Key is the full path
    The key is composed of prefix + object name
    No concept of directories in buckets

    Object values are the content of the body:
        Max object size is 5TB
        If uploading more, must use multi-part upload

    Metadata (list of text key/value pairs - system or user metadata)
    Tags (Unicode key / value pair - up to 10) - useful for security/lifecycle
    Version ID (if versioning is enabled)

S3 - Security

    User Based
        IAM Policies - which API calls should be allowed for a specific user from IAM

    Resource Based
        Bucket Policies - bucket wide rules from the S3 console - allows cross account
        Object Access Control List (ACL) - finer grain (can be disabled)
        Bucket Access Control List (ACL) - less common (can be disabled)

    An IAM principal can access an S3 object if
        The user IAM permissions allow it or the resource policy allows it, and there's no explicit deny

    Encryption: encrypt objects in Amazon S3 using encryption keys

S3 Bucket Policies

    JSON based policies
        Resources: buckets or objects
        Effect: Allow / Deny
        Actions: Set of API to allow or deny
        Principal: The account or user to apply the policy to

    Use S3 bucket for policy to:
        Grant public access to the bucket
        Force objects to be encrypted at upload
        Grant access to another account (Cross account)

S3 Durability and Availability

    Durability
        High durability of objects across multiple AZ
        If you store 10 million objects with Amazon S3, you can on average expect to incur a loss of a single object once every 10000 years
        Same for all storage classes

    Availability
        Measures how readily available a service is
        Varies depending on storage class
        Eg: S3 standard has 99.99% availability = not available 53 minutes a year

S3 Standard - General Purpose

    99.99% Availability
    Used for frequently accessed data
    Low latency and high throughput
    Sustain 2 concurrent facility failures
    Use cases: big data analytics, mobile & gaming applications, content distribution

S3 Storage Classes - Infrequent Access

    For data that is less frequently accessed, but requires rapid access when needed
    Lower cost than S3 Standard

    Amazon S3 Standard-Infrequent Access (S3 Standard-IA)
        99.9% availability
        Use cases: Disaster recovery, backups

    Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA)
        High durability in a single AZ, data lost when AZ is destroyed
        99.5% availability
        Use cases: Storing secondary backup copies of on-premise data, or data you can recreate

Glacier Storage Classes

    Low-cost object storage meant for archiving/backup
    Pricing: price for storage + object retrieval cost

    Amazon S3 Glacier Instant Retrieval
        Millisecond retrieval, great for data accessed once a quarter
        Minimum storage duration of 90 days

    Amazon S3 Glacier Flexible Retrieval
        Expedited (1 to 5 minutes), Standard (3 to 5 hours), Bulk (5 to 12 hours) - free
        Minimum storage duration of 90 days

    Amazon S3 Glacier Deep Archive - for long term storage:
        Standard (12 hours), Bulk (48 hours)
        Minimum storage duration of 180 days

S3 Intelligent-Tiering

    Small monthly monitoring and auto-tiering fee
    Moves objects automatically between Access Tiers based on usage
    There are no retrieval charges in S3 Intelligent-tiering

        Frequent Access tier (automatic): default tier
        Infrequent Access tier (automatic): objects not accessed for 30 days
        Archive Instant Access tier (automatic): objects not accessed for 90 days
        Archive Access tier (optional): configure from 90 days to 700+ days
        Deep Archive Access tier (optional): config from 180 days to 700+ days

IAM Access Analyser for S3

    Ensures that only intended people have access to your S3 buckets
    Eg: publicly accessible bucket, bucket shared with other AWS account
    Evaluates S3 Bucket policies, S3 ACLs, S3 Access Point Policies
    Powered by IAM Access Analyser

Shared Responsibility Model for S3

AWS
Infrastructure (global security, durability, availability, sustain concurrent loss of data in two facilities)
Configuration and vulnerability analysis
Compliance validation

User
S3 Versioning
S3 Bucket Policies
S3 Replication Setup
Logging and Monitoring
S3 Storage Classes
Data encryption at rest and in transit

AWS Snow Family
Highly-secure, portable devices to collect and process data at the edge, and migrate data into and out of AWS

    Data migration: Snowcone, Snowball Edge, Snowmobile
    Edge Computing: Snowcone, Snowball Edge

Edge Computing

    Process data while it's being created on an edge location
    These location may have
        Limited/no internet access
        Limited/no easy access to computing power

    Use cases of Edge Computing
        Preprocess data
        Machine learning at the edge
        Transcoding media streams
