# Message Queues
---

## What does it mean that web sockets are bidirectional? Why is this useful?

Web sockets a a means of two-way communication over a single connection. This allows events to be both emitted and listened for at the same time.

## Does socket.io use HTTP? Why?

It does use HTTP, because it has two components, a server side and a client side. The client-side component runs in the browser.

## What happens when a client emits an event?

When a client emits an event it will be heard by the server it is connected to, which may in turn result in the server emitting an event of its own or rebroadcasting the same event.

## What happens when a server emits an event?

When a server emits an event, it is either emitted to all clients connected to the server, or it is emitted to a single client through a specified socket for that client or subscriber group.

## What happens if a client “misses” an event?

If a client missed an event it is known as an unhandled message and is ignored as if there were no event handler for the event.

## How can we mitigate this?

We should always have handlers installed for all events, and determine within those handlers whether the event should be responded to.


## Vocabulary Terms
| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Socket** | *A server typically "listens" to a socket bound to a specific port number for a client to make a connection request. When a new client makes a connection to the server a new socket is created for that client to communicate with the server.* [*Oracle*](https://docs.oracle.com/javase/tutorial/networking/sockets/definition.html) |
| **Web Socket** | *a full-duplex (two-way) communication channel on a single TCP connection.* [*Wikipedia*]([*Wikipedia*](https://en.wikipedia.org/wiki/Event_driven_programming)) |
| **Socket.io** | *A library that allows event-based two-way communication between a client and a server* |
| **Client** | *A separate machine, computer or application that connects to and communicates/interacts with a server.* ) |
| **Server** | *A computer or program that acts as a hub that multiple clients can connect to.* |
| **OSI Model** | *A conceptual model of the communication functions of a  computing system with the goal of interoperability of diverse communication systems with standard communication protocols.* [*Wikipedia*](https://en.wikipedia.org/wiki/OSI_model) |
| **TCP Model** | *A model that provides end-to-end data communication specifying how data should be packetized, addressed, transmitted, routed, and received.* [*Wikipedia*](https://en.wikipedia.org/wiki/Internet_protocol_suite) |
| **TCP** | *A connection between client and server. The server must be listening (passive open) for connection requests from clients before a connection is established by way of a three-way handshake.* [*Wikipedia*](https://en.wikipedia.org/wiki/Transmission_Control_Protocolhttps://en.wikipedia.org/wiki/Transmission_Control_Protocol) |
| **UDP** | *provides a connectionless communication model with few protocol mechanisms, that prioritizes time over reliability.* [*Wikipedia*](https://en.wikipedia.org/wiki/User_Datagram_Protocol) |
| **Packets** | *A formatted unit of data that consists of control information(ie. headers) and data(payload).* |

[Back to Main](../README.md)