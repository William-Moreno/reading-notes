# AWS: Cloud Servers
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
| **Server** | *A piece of computer hardware or software that provides functionality for other programs or devices, called "clients".* [*Wikipedia*](https://en.wikipedia.org/wiki/Server_(computing)#:~:text=In%20computing%2C%20a%20server%20is,called%20the%20client%E2%80%93server%20model.) |
| **Pub/Sub** | *An asynchronous messaging service available in all Google Cloud regions that offers durable message storage and "real-time" message delivery.* [Google Cloud Docs](https://cloud.google.com/pubsub/docs/overview) |
| **WRRC** | *Web Request Response Cycle. The web is a cycle where the requests and responses of clients and servers flow from and to each other.* [*"The Request/Response Cycle of the Web*](https://medium.com/@jen_strong/the-request-response-cycle-of-the-web-1b7e206e9047#:~:text=The%20web%20is%20a%20cycle,What%20is%20a%20client%3F&text=Generally%2C%20clients%20are%20web%20browsers,(when%20making%20cURL%20requests).) |


[Back to Main](../README.md)