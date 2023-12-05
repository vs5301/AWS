Amazon SQS

    Fully managed (serverless), used to decouple applications
    Scales from one message per second to 10000s per second
    Default retention of messages: 4 days, max of 14 days
    No limit to how many messages in queue
    Messages are deleted after they're read by customers
    Low latency

Amazon Kinesis

    Kinesis -> real-time big data streaming
    Managed service to collect, process, and analyse real-time streaming data at any scale

Amazon SNS

    "Event publishers" only sends message to one SNS topic
    As many "event subscribers" as wanted to listen to SNS topic notifications
    Each subscriber to topic will get all messages
    Up to 12500000 subscriptions per topic, 100000 topics limit

Amazon MQ

    SQS, SNS are "cloud-native" services: proprietary protocols from AWS
    Traditional applications running from on-premises may use open protocols such as: MQTT,AMQP,STOMP,Openwire,WSS
    When migrating to the cloud instead of re-engineering the application to use SQS and SNS, we can use Amazon MQ
    Amazon MQ is a managed message broker service for RabbitMQ & ActiveMQ
    It doesn't scale as much as SQS/SNS
    Runs on servers, can run in multi-AZ with failover
    Has both queue feature (SQS) and topic features (SNS)
