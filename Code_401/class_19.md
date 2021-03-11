# AWS: Events
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
| **Serverless API** | *An API server which runs in event-triggered, stateless containers that are fully managed by cloud providers. AWS API Gateway and Lambda functions are examples of a serverless API.* |
| **Triggers** | *A Lambda resource or a resource in another service that can be configured to invoke a function in response to lifecycle events, external requests, or on a schedule.* [AWS](https://docs.aws.amazon.com/lambda/latest/dg/lambda-invocation.html) |
| **Dynamo vs Mongo** | *DynamoDB uses tables, items and attributes as the core components(key/value pairs) and uses primary keys to uniquely identify each item in a table. MongoDB uses JSON-like documents to store schema-free data, as collections of documents are not required to adhere to any predefined structure.* [panoply blog](https://blog.panoply.io/dynamodb-vs-mongodb) |
| **Dynamoose vs Mongoose** | *Dynamoose is a modeling tool npm package for Amazon's DynamoDB that is heavily inspired by the mongoose npm package, which performs the same duties for MongoDB.* |


## I Am Most Excited About Trying to Implement or See How These Work:

- I am very interested in seeing how SNS and SQS can be utilized to do the same tasks we have worked on in the past.


[Back to Main](../README.md)