ECS -> Elastic Container Service

    Launch Docker containers on AWS
    You mush provision & maintain the infrastructure (the EC2 instances)
    AWS takes care of starting/stopping containers
    Has integrations with the Application Load Balancer
    Exam top -> Anytime user wants to run Docker containers on an instance -> ECS

Fargate

    Launch Docker containers on AWS
    You do not provision the infrastructure (no EC2 instances to manage)
    Serverless offering
    AWS just runs containers for you based on the CPU/RAM you need

ECR -> Elastic Container Registry

    Private Docker Registry on AWS
    There is where you store your Docker images so they can be run by ECS or Fargate

Serverless -> New paradigm in which developers don't have to manage servers anymore
Initialy serverless == FaaS (Function as a Service)

AWS Lambda

    Virtual functions -> no servers to manage
    Limited by time -> short executions
    Run on-demand
    Scaling is automated

    Benefits:
    Easy Pricing
        Pay per request and compute time
        Free tier of 1000000 AWS Lambda requests and 400000 GBs of compute time
    Integrated with the whole AWS suite of services
    Event-Driven: functions get invoked by AWS when needed
    Integrated with many programming languages
    Easy monitoring through AWS CloudWatch
    Easy to get more resources per functions (up to 10GB of RAM)
    Increasing RAM will aslo improve CPU and network

    Lambda Container Image
        Container image must implement the Lambda Runtime API
        ECS/Fargate is preferred for running arbitrary Docker images

    Lambda pricing based on calls and duration, usually very cheap to run AWS Lambda

Amazon API Gateway

    Fully managed service for developers to easily create, publish, maintain, monitor, and secure APIs
    Serverless and scalable
    Supports RESTful APIs and WebSocket APIs
    Support for security, user authentication, API throttling, API keys, monitoring
    Exam tip -> A way to create serverless API -> API Gateway & Lambda

AWS Batch

    Fully managed batch processing at any scale
    Efficiently run 100000s of computing batch jobs on AWS
    A "batch" job is a job with a start and an end (opposed to continuos)
    Batch will dynamically launch EC2 instances or Spot instances
    AWS Batch provisions the right amount of compute/memory
    Batch jobs are defind as Docker images and run on ECS
    Helpful for cost optimizations and focusing less on the infrastructure

Amazon Lightsail

    Virtual servers, storage, databases, and networking
    Low & predictable pricing
    Simpler atlernative to using EC2,RD2,ELB,EBS,Route 53...
    Great for people with little cloud experience
    Can setup notifications and monitoring of your Lightsail resources
    Use cases:
        Simple web applications
        Websites
        Dev/Test environment
    Has high availability but no auto-scaling, limited AWS integrations
    Exam tip -> Any question where user has no cloud experience and needs to get started quickly -> Lightsail
