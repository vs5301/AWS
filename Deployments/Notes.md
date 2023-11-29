CloudFormation
Declarative way of outlining your AWS infrastructure for any resources

Benefits

    Infrastructure as code
        No resources are maunally created which is excellent for control
        Changes to the infrastructure are reviewed through code

    Cost
        Each resource within the stack is tagged with an identifier so you can easily see how much a stack costs you
        You can estimate the costs of your resources using the CloudFormation template
        Savings strategy: In Dev, you could automate deletion of templates at 5 pm and recreate them at 8 am next day

    Productivity
        Ability to destroy and re-create infrastructure on the cloud
        Automated generation of diagram for templates
        Declarative programming

Exam tip -> CloudFormation is used when we have infrastructure as code or we need to repeat an architechture in different environment, regions or even AWS accounts.

AWS Cloud Development Kit (CDK)
Define your cloud infrastructure using a familiar language, code is compiled into a CloudFormation template (JSON/YAML)

    Great for Lambda functions and Docker containers in ECS/EKS

Beanstalk - Platform as a Service

    Managed service
        Instance configuration / OS is handled by Beanstalk
        Deployment strategy is configurable but performed by Elastic Beanstalk
        Capacity provisioning
        Load balancing and auto scaling
        Application health-monitoring and responsiveness
    Just the application code is the responsibility of the developer
    Beanstalk has health monitoring, health agent pushes metrics to CloudWatch

AWS CodeDeploy

    We want to deploy application automatically
    Works with EC2 instances
    Works with On-Premises servers
    Hybrid service
    Servers/Instances must be provisioned and configured ahead of tiem with teh CodeDeploy Agent

AWS CodeCommit

    Source-control service that hosts Git-based repositories
    Easy to collaborate with others on code
    Code changes automatically versioned
    Fully manages, scalable & highly available
    Private, secured & integrated with AWS

AWS CodeBuild

    Code building service in the cloud
    Compiles source code, run tests, and produces packages that are ready to be deployed
    Fully managed, serverless
    Continuously scalable & highly available
    Secure, pay-as-you-go pricing - only pay for the build time

AWS CodePipeline

    Orchestrate the different steps to have the code automatically pushed to production
    Fully managed, compatible with other AWS services and custom plugins
    Fast delivery and rapid updates
    Exam tip -> orchestration of code -> CodePipeline

Storing and retrieving dependencies and software packages that depend on each other to be built and for new ones to be created, is called artifact management

AWS CodeArtifact

    Secure, scalable and cost-effective artifact management
    Works with common dependency management tools
    Developers and CodeBuild can then retrieve dependencies straight from CodeArtifact

AWS CodeStar

    Unified UI to easilt manage software development activities in one place
    Can edit the code "in-the-cloud" using AWS Cloud9
    Exam tip -> CodeStar is a central service that allows developers to quickly start development using the best CICD practices

AWS Cloud9

    Cloud IDE for writing, running and debugging code
    Allows for code collaboration

AWS Systems Manager (SSM)

    Helps manage EC2 and On-premises systems at scale
    Hybrid AWS service
    Opertaional insights about the state of your infrastructure
    Patching automation for enhanced compliance
    Run commands across an entire fleet of servers
    Store parameter configuration with the SSM Parameter Store
    Exam tip -> Way to patch fleet of EC2 instances or on-premises servers -> SSM

SSM Session Manager

    Allows you to start a secure shell on your EC2 and on-premises servers
    No SSH access, bastion hosts or SSH keys needed

Systems Manager Parameter Store

    Secure storage for configuration and secrets
    API keys, passwords, configurations
    Serverless, scalable, durable, easy SDK
    Controll access permissions using IAM
    Version tracking and encryption

AWS OpsWorks

    Chef and Puppet help you perform server configuration automatically, or repetitive actions
    Work grate with EC2 and on-premises VM
    AWS OpsWorks = Managed Chef and Puppet
    Exam tip -> Chef or Puppet needed -> AWS OpsWorks
