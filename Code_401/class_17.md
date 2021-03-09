# AWS: S3 and Lambda
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
| **Server Instances** | *These are copies of the software required to perform the server's functions. Each copy of the program currently active on either a virtual server/machine or physical computer is considered a 'server instance'*  |
| **Containers** | *Standardize and simplify the deployment of code, sometimes even full applications, to the cloud without requiring any changes to its original code.* [Containers on AWS](https://aws.amazon.com/containers/) |
| **Cloud Services** | *Infrastructure, platforms, or software that are made available by third-party providers, available to customers via the internet. They facilitate data flow between clients and servers and are accessible to anyone with a computer, OS and internet connection* [*RedHat*](https://www.redhat.com/en/topics/cloud-computing/what-are-cloud-services).) |
| **Cloud Architecture** | *Refers to the various components, such as databases, applications, platforms, available to both front-ends and back-ends and their relationship to each other (ie. network) within the cloud.* [*Wikipedia*](https://en.wikipedia.org/wiki/Cloud_computing_architecture) |
| **AWS** | *Amazon Web Services. Provides a highly reliable and scalable, cloud-based  infrastructure* [AWS](https://aws.amazon.com/) |
| **EC2/Beanstalk vs Heroku** | *Heroku is a container-based cloud platform/AWS is a secure cloud services platform. Heroku offers a ready-to-use environment that is fast to deploy code on/AWS deployment service is relatively more complicated. Heroku is most suitable to startups and medium-sized businesses/AWS focuses mainly on medium to very large businesses. Heroku can meet low computational demands/AWS is capable of meeting very high demands. Heroku does not require infrastructure maintenance/AWS essentially needs a capable DevOps. Heroku does not support as many geographical regions as AWS.* [*"Heroku vs AWS*](https://www.guru99.com/heroku-vs-aws.html) |

## 3 Things I Had Previously Heard of and Now Have Better Clarity On

1. S3 is a service provided by Amazon AWS that provides a scalable, durable and avialable object storage service
1. AWS Lambda is a serverless computing service that enables users to created and execute self-contained functions to perform a variety of tasks
1. CDNs are content delivery networks and that they improve website loading times as well as content delivery speeds

## 3 Things I Am Hoping to Learn More About in the Upcoming Lecture

1. How AWS Lambda works and practical usage examples
1. How to utilize Lambda in conjunction with DynamoDB and API Gateway to replicate and improve work and projects we have already built in another way/environment
1. How to determine the average size of payloads being passed by functions within my code

## I Am Most Excited About Trying to Implement or See How These Work:

- Perhaps using Lambda, DynamoDB and API Gateway in concert to rebuild and improve one of my previous projects


[Back to Main](../README.md)