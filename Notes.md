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
