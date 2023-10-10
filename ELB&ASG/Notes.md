Scalability & High Availability

    Scalability means an application/system can handle greater loads by adapting.
    Types:
        Vertical Scalability
        Horizontal Scalability (elasticity)
    Scalability is linked but different from High Availability

    Vertical Scalability

        Means increasing the size of the instance
        Eg, application runs on t2.micro, scaling the application vertically means now it runs on t2.large
        Vertical scalability is very common for non distributed systems, such as databases.
        Usually a limit to how much you can vertically scale (hardware limit)

    Horizontal Scalability

        Means increasing number of instances/systems for your application
        Implies distributed systems
        Very common for web applications/modern applications
        Easy to horizontally scale due to cloud offerings such as Amazon EC2

    High Availability

        Goes hand in hand with horizontal scaling
        Means running your application/system in at least 2 availability zones
        Goal is to survive a data center loss

Scalability vs Elasticity vs Agility

    Scalability: ability to accomodate a larger load by making the hardware stronger (scale up), or by adding nodes (scales out)

    Elasticity: once a system is scalable, elasticity means that there will be some "auto-scaling" so that the system can scale based on the load. This is "cloud-friendly": pay-per-use, match demand, optimize costs

    Agility: (not related to scalability - distractor): new IT resources are only a click away, which means that you reduce the time to make those resources available to your developers from weeks to just minutes

Elastic Load Balancer

    Load balancers are servers that forward internet traffic to multiple servers (EC2 instances) downstream

    Why use a load balancer

        Spread load across multiple downstream instances
        Expose a single point of access (DNS) to your application
        Seamlessly handle failures of downstream instances
        Do regular health checks to your instances
        Provide SSL termination (HTTPS) for your websites
        High availability across zones

    Why use an Elastic Load Balancer

        An ELB is a managed load balancer
            AWS guarantees that it will be working
            AWS takes care of upgrades, maintenance, high availability
            AWS provides only a few configuration knobs

        It costs less to setup your own load balancer but it will be a lot more effort on your end (maintenance, integrations)

        4 kinds of load balancers offered by AWS:
            Application load balancer (HTTP/HTTPS only) - Layer 7
            Network Load Balancer (ultra-high performance, allows for TCP/UDP) - Layer 4
            Gateway Load Balancer - Layer 3
            Classic Load Blancer (retired in 2023) - Layer 4 & 7
