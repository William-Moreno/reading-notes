# AWS: API, Dynamo and Lambda
---

## What is the Difference between FIFO and Standard Queues?

FIFO queues have the same features as standard queues. However, they also support "exactly-once" processing and ordering of the queue. FIFO queues also have options that help prevent duplicate messages from being generated or received.

- [aws.amazon.com](https://aws.amazon.com/about-aws/whats-new/2016/11/amazon-sqs-introduces-fifo-queues-with-exactly-once-processing-and-lower-prices-for-standard-queues)

## How Can the Server Be Assured a Message Was Properly Received?

Subscribers to the messages should be configured to emit a "received' event back to the server to confirm receipt of a message. Upon detecting the "received" event, the server can then safely remove the message from the queue.

## What Classic Design Pattern is Best Represented by Event Driven Programming?

Event driven programming best represents the **observer pattern** of software design, in which a *subject* maintains a list of its *observers* and notifies them automatically of any state changes, typically by calling one of their methods.

[Wikipedia](https://en.wikipedia.org/wiki/Observer_pattern)

## How Do You Test an Event Driven System?

The easiest tests to implement on event driven systems are unit tests which test individual components of differing parts of the sytems. Tests can be performed to verify the server and clients are communicating correctly. Otherwise, event changes can be mocked or simulated and the resulting output from the system can be observed/monitored.

[*"Testing Event-Driven Systems"*](https://medium.com/dan-on-coding/testing-event-driven-systems-63c6b0c57517)

## Vocabulary Terms
| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Serverless Functions** | *Single-purpose functions that are hosted on managed infrasctructure, that are invoked through the internet. They are hosted and maintained by cloud computing companies, such as **Lambda for AWS**. They are integral to "Microservice Architecture".* [PubNub](https://www.pubnub.com/blog/what-is-a-serverless-function/) |
| **Cloud Storage** | *A computing model which store data on the internet trough a cloud computing provider that manages and operates data storage as a service. It provides data storage infrastructure, allowing for more agility, scalability and durability throughout the world.* [Containers on AWS](https://aws.amazon.com/what-is-cloud-storage/) |
| **CDN** | *Content Delivery Network. A group of servers in differing geographical locations that work together to delivery web content as well as data and files quickly and efficiently to users.* |


## 3 Things I Had Previously Heard of and Now Have Better Clarity On

1. API Gateway is another managed service from Amazon that can take the place of API servers, both RESTful and WebSocket.
1. AWS Lambda is a serverless computing service that enables users to created and execute self-contained functions to perform a variety of tasks
1. DynamoDB is a NoSQL database service offered by AWS that works well with AWS Lambda.

## 3 Things I Am Hoping to Learn More About in the Upcoming Lecture

1. How API Gateway handles authentication and access control
1. How the GUI interface for API Gateway allows users to *"...sketch out the API structure and view the API flows in graphical form..."*.
1. How to determine the average size of payloads being passed by functions within my code

## I Am Most Excited About Trying to Implement or See How These Work:

- Using Lambda, DynamoDB and API Gateway in concert to rebuild and improve one of my previous projects or create a new one


[Back to Main](../README.md)