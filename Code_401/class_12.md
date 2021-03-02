# Socket.io
---

## What is the Benefit of Transforming Data into Packets?

Packets reliably and efficiently transfer data. Large files are broken into and sent in smaller packets, helping ensure each section is transmitted successfully. If a packet is not received, only the missing packet needs to be resent. Also, when a data transfer encounters network congestion caused by multiple simultaneous transfers, remaining packets can be rerouted through a less congested path.

- [Tech Terms](https://techterms.com/definition/packet)

## Why is UDP Often Referred to as a Connectionless Protocol?

UDP does not establish connections before seding data. Therefore, it is called a "Connectionless" protocol.

- [Wikibooks](https://en.wikibooks.org/wiki/Communication_Networks/TCP_and_UDP_Protocols/UDP)

## Can a Socket Server Application have Multiple Socket Connections?

Even though, the server socket listens on a single port on it's side of a connection, multiple client-side connections can be made to that single port.

[Stack Overflow](https://stackoverflow.com/questions/11129212/tcp-can-two-different-sockets-share-a-port)

## Can a Socket Connection Application be Connected to Multiple Socket Server?

If the application is a client to multiple servers, it should utilize one socket per server. 

[Stack Overflow](https://stackoverflow.com/questions/5402019/connecting-to-multiple-servers-from-a-single-client-socket-c)

## Can an Application be Both a Socket Server and a Socket Connection?

Yes. A client socket and a server socket can be used within a single application, using two different ports. This can also ba accomplished if the sockets won't be using the same port at the same time.

- [Quora](https://www.quora.com/Can-you-make-a-client-socket-and-a-server-socket-in-one)

## Vocabulary Terms
| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Observer Pattern** | *A software design pattern in which an object, named the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods. It is mainly used for implementing distributed event handling systems, in "event driven" software.* [*Wikipedia*](https://en.wikipedia.org/wiki/Observer_pattern) |
| **Listener** | *A function that waits (or listens) for a specific event to occur and then typically cues an event handler.* |
| **Event Handler** | *A callback function that is usually called by an event listener following the initiation of an event* |
| **Event Driven Programming** | *A programming paradigm in which there is generally a main loop that listens for events and then triggers a callback function when one of those events is detected.* [*Wikipedia*](https://en.wikipedia.org/wiki/Event_driven_programming) |
| **Event Loop** | *A programming construct or design pattern that waits for and dispatches events or messages in a program. Sometimes called the Main (Event) Loop.* [*Wikipedia*](https://en.wikipedia.org/wiki/Event_loop) |
| **Event Queue** | *This is where your asynchronous code gets pushed to, and waits to be inserted to the call stack.* [*medium.com*](https://medium.com/@Rahulx1/understanding-event-loop-call-stack-event-job-queue-in-javascript-63dcd2c71ecd) |
| **Call Stack** | *where all the synchronus javascript code gets pushed and executed one by one as the interpreter reads the program. Each gets popped out once its execution is done.* [*medium.com*](https://medium.com/@Rahulx1/understanding-event-loop-call-stack-event-job-queue-in-javascript-63dcd2c71ecd) |
| **Emit/Raise/Trigger** | ** [*Wikipedia*](https://en.wikipedia.org/wiki/Role-based_access_control) |
| **Subscribe** | *subscribers listen for events to emit from a "publisher".* |
| **database** | ** [*Wikipedia*](https://en.wikipedia.org/wiki/Capability-based_security) |