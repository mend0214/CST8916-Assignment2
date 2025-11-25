# Assignment 2: Cloud Service Providers Comparison Report

## Executive Summary
AWS, Azure, and GCP each offer comprehensive platforms for RESTful APIs, GraphQL, WebSockets, data streaming, and stream analytics. AWS API Gateway provides a fully managed environment for creating and securing RESTful APIs with no minimum fees and tiered per-request pricing; it also offers lower-cost HTTP APIs. Azure API Management includes an API gateway, management plane, and customizable developer portal, with fixed-price tiers and a serverless Consumption option. GCP API Gateway delivers REST API hosting with per-call pricing and discounted rates at high volume.

For GraphQL, AWS AppSync offers a fully managed, serverless GraphQL service with real-time subscriptions. Azure lacks a native service but supports GraphQL through hosted servers or API Management’s Synthetic GraphQL. GCP supports GraphQL via Apigee and by hosting GraphQL servers on Cloud Run, GKE, or App Engine.

For WebSockets, AWS provides API Gateway WebSocket APIs for bidirectional communication with automatic scaling. Azure offers Web PubSub, a fully managed service with manual and autoscaling options. GCP lacks a native WebSocket service but supports WebSockets via Cloud Run, App Engine, GKE, and Compute Engine.
In data streaming, AWS Kinesis handles real-time ingestion of large-scale event streams, Azure Event Hubs supports millions of events per second, and GCP Pub/Sub provides scalable asynchronous messaging. For stream analytics, AWS offers Managed Service for Apache Flink, Azure provides Stream Analytics for low-latency processing, and GCP delivers Dataflow using Apache Beam for unified batch and streaming pipelines.
For use cases, Azure Web PubSub is recommended for real-time chat applications, while AWS AppSync is preferred for cost-efficient, scalable GraphQL APIs.

## Introduction
In this report we compare the different services provided by AWS, Azure and GCP. First, we compare RESTful API services, the different API Gateway services and management tools they provide, and their pricing models. Second, we compare GraphQL services, if the cloud provider has native GraphQL support and third-party integration options. Third, we compare WebSocket services, real-time communication platforms and scalability features. Fourth, we compare data streaming services, their different streaming platforms and data ingestion capabilities. Lastly, we compare different real-time analytics platforms. We also examine real-world use cases of real-time applications and analyze which of service of which cloud provider is best for the purpose.

## RESTful API Services
AWS provides API Gateway which is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as a front door for applications to access data from backend services. API Gateway allows you to create RESTful APIs, supports containerized and serverless workloads, and web applications. API Gateway offers Portals that enable consumers to create fully managed AWS-native portals for developers. API Gateway handles everything from accepting and processing concurrent API calls, traffic management, authorization and access control, monitoring, and API version management. API Gateway has no minimum fees or start up costs but charges for the API calls you receive with tiered pricing model, customers can reduce cost as their usage scales, for example API Requests price can be as low as $0.90 per million requests at the highest tier. AWS also offers is also a cheaper option for RESTful APIs called HTTP APIs [1].

Azure provides API Management which is made up of an API gateway, a management plane, and a developer portal. All requests from client applications go to the API gateway, which then forwards them to respective backend services. The gateway enables consistent configuration of routing, security, throttling, caching, and observability. Azure also has an open-source developer portal which consumers can customize. The portal allows them to read API documentation, call an API through interactive consoles, create an account to get API keys, access usage analytics, and manage API keys. Azure API Management offers various pricing tiers such as ‘Classic and ‘V2’ that have fixed monthly cost and includes different features, performance, capacity limits and scalability. It also offers a serverless ‘Consumption’ tier that bills per execution [2].

GCP provides API Gateway which is a management system that provides hosting, logging, monitoring, security and other features built into the Google Cloud Platform to enable consumers to provide secure access to services through a well-defined REST API. GCP API Gateway offers per-call pricing, it costs $0 per million calls from 0-2 million calls, it costs $3.00 per million calls from 2 million to 1 billion calls, and it costs $1.50 per million calls from 1 billion calls and over [3].

## GraphQL Services
AWS provides AWS AppSync which is a fully managed, serverless GraphQL service that enables developers to connect their applications and services to GraphQL APIs. AppSync offers simplified data access and querying and WebSocket for GraphQL subscriptions and pub/sub channels. AWS offers hosting GraphQL servers like Apollo Server in EC2, ECS, and Lambda [4].

Azure API Management can be used to front, build, or manage a GraphQL API for an existing GraphQL backend and it also has a feature called ‘Synthetic GraphQL’ which creates a GraphQL layer over non-GraphQL data sources like REST APIs, Azure Cosmos DB, Azure SQL etc. and involves creating a GraphQL schema and resolvers for each field in the schema. Customers can also GraphQL yourself by deploying a GraphQL server using Apollo Server or HotChocolate on Azure hosting platforms like Azure App Service, Azure Functions, and Azure Kubernetes Service for containerized solutions [5].

Google Cloud Provider provides several services to support GraphQL. First, Apigee API management which offers native support for GraphQL APIs. Second, is hosting GraphQL servers such as Apollo Server or GraphQL Yoga in GCP services such as Cloud Run, Google Kubernetes Engine (GKE), and App Engine [6].

## WebSocket Services
In AWS API Gateway, you can create a WebSocket API as a stateful frontend for AWS services or an HTTP endpoint. WebSocket APIs are bidirectional where a client can send messages to a service and services can send messages independently to clients. These are often used in real-time applications such as chat applications, multiplayer games, and financial trading platforms. API Gateway offers automatic scaling that automatically scales resources up or down based on traffic [7].

Azure Web PubSub is a fully managed service that supports native and serverless WebSockets that allows developers to create loosely coupled and scalable real-time applications. Azure Web PubSub handles hosting, scalability, load balancing and other tasks. On top of manual scaling which allows customers to assign a fixed number of resources to the service, Web PubSub offers autoscaling that allows customers to set conditions that will dynamically change the units allocated to the Web PubSub service [8].

GCP does not offer native WebSocket services such as AWS API Gateway WebSocket API and Azure Web PubSub but offers alternatives such as Cloud Run that can host containerized applications that use WebSockets, App Engine also supports WebSockets in the environment and can host real-time applications. Compute Engine and Google Kubernetes Engine also offer the same support. Cloud Run is a serverless platform that offers automatic scaling based on demand and load balancing that distributes traffic across multiple backend instances.

## Data Streaming services
Amazon Kinesis Data Streams collects and process large streams of data records in real time. The type of data used can include IT infrastructure log data, application logs, social media, market data feeds, and web clickstream data [9].

Azure Event Hubs is a native data-streaming service. This service can handle and ingest millions of events per second, continuously ingress data from any source to any destination with low latency and configurable time retention [10].

GCP Pub/Sub is an asynchronous and scalable messaging service that decouples services producing messages from services processing those messages. This can be used for streaming analytics and data integration pipelines to load and distribute data [11].

## Stream Analytics
AWS has Managed Service for Apache Flink which is a fully managed Amazon service that lets you use an Apache Flink application to process streaming data. An Apache Flink application is a Java or Scala application that is created with the Apache Flink framework using either DataStream API or the Table API [12].

Azure has Azure Stream Analytics which is a fully managed stream processing enigne that is designed to analyze and process large volumes of streaming data with sub-millisecond latencies. Customers can build a streaming pipeline using Stream Analytics to identify patterns and relations in data that originates from applications, devices, sensors, clickstreams, and social media feeds [13].

GCP has Dataflow which is a service that provides unified stream and batch data processing at scale. It uses the Apache Beam SDK, an open-source programming model that enables customers to develop both batch and streaming pipelines. The pipelines created using the Apache Beam program are run on the Dataflow service [14].

## Use Case Analysis
When developing a real-time chat application such as Facebook messenger or Discord, I recommend using Azure Web PubSub. First, it is cost-effective as it offers Free tier for development and Premium tier for production workloads. It uses a pricing model that calculates cost based on the number of units used per day. Second, the Azure infrastructure manages connections, scaling, load balancing, and lifecycle therefore it can handle large-scale client connections.  Third, it is designed for publish-subscribe patterns making it suitable for broadcasting messages to multiple clients in a chat scenario. Lastly, it is heavily integrated with the Azure ecosystem so it can access other services such as Azure Functions for backend logic or Azure AI services for features like translation.

When developing a GraphQL API for the backend services of an application, I recommend using AWS AppSync. First, it uses pay-per-request pricing making it more cost effective than hosting GraphQL server using other services with other cloud providers. Second, AppSync optimizes resolver executions internally making it faster than hosted GraphQL servers. Third, it can easily be integrated with your application backend services using HTTP endpoints. Lastly, it can easily be integrated with other services in AWS ecosystem such as DynamoDB for data resource, Lambda for backend logic, and Cognito for security.

## Conclusion
Overall, AWS, Azure, and GCP each offer mature and feature-rich solutions for API management, GraphQL services, real-time messaging, data streaming, and stream analytics, but they differ in their approaches and strengths. AWS provides the most comprehensive native offerings across all categories, particularly with AppSync for GraphQL and Kinesis paired with Apache Flink for real-time data processing. Azure excels in API lifecycle management and delivers a robust, fully managed WebSocket service through Web PubSub, making it ideal for large-scale real-time communication workloads. GCP emphasizes simplicity and scalability, offering flexible hosting options for GraphQL and WebSockets along with powerful data processing through Pub/Sub and Dataflow. Ultimately, the best platform depends on an application’s specific requirements: Azure is well suited for real-time, connection-heavy applications such as chat systems; AWS is the strongest choice for GraphQL-driven backends and event streaming; and GCP is a strong fit for scalable, data-centric pipelines. Each cloud provider can support real-time and API-intensive workloads, but their native tooling and cost structures guide which platform delivers the most efficient and streamlined solution for a given use case.

## References
[1] “API Management - Amazon API Gateway - AWS,” Amazon Web Services, Inc. https://aws.amazon.com/api-gateway/

[2] Dlepow, “Azure API Management - Overview and Key concepts,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/api-management/api-management-key-concepts

[3] “API Gateway documentation  |  Google Cloud Documentation,” Google Cloud Documentation. https://docs.cloud.google.com/api-gateway/docs

[4] “What is AWS AppSync? - AWS AppSync GraphQL.” https://docs.aws.amazon.com/appsync/latest/devguide/what-is-appsync.html

[5] Dlepow, “Support for GraphQL APIs - Azure API Management,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/api-management/graphql-apis-overview

[6] “Using GraphQL,” Google Cloud Documentation. https://docs.cloud.google.com/apigee/docs/api-platform/develop/graphql

[7] “API Gateway WebSocket APIs - Amazon API Gateway.” https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api.html

[8] Kevinguo-Ed, “What is Azure Web PubSub service?,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/azure-web-pubsub/overview

[9] “What is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams.” https://docs.aws.amazon.com/streams/latest/dev/introduction.html

[10] Spelluru, “Azure Event Hubs: Data streaming platform with Kafka support - Azure Event Hubs,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/event-hubs/event-hubs-about

[11] “What is Pub/Sub?,” Google Cloud Documentation. https://docs.cloud.google.com/pubsub/docs/overview

[12] “Managed Service for Apache Flink: How it works - Managed Service for Apache Flink.” https://docs.aws.amazon.com/managed-flink/latest/java/how-it-works.html

[13] AliciaLiMicrosoft, “Introduction to Azure Stream Analytics - Azure Stream Analytics,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction

[14] “Dataflow overview,” Google Cloud Documentation. https://docs.cloud.google.com/dataflow/docs/overview

## Use of Generative AI
- Generated Executive Summary and Conclusion
- Brainstorming ideas for WebSockets and Data Streaming Services
