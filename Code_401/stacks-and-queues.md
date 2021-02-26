# Stacks and Queues
---

## What is a Stack

Stacks are data structures that consist of nodes. Each node in the stack references the next node below it (next), but woes not reference the node above it (previous). Stacks follow **FILO/LIFO** rules where:

  - The first node pushed/added to a stack will be the last one popped out
  - The last node pushed/added to a stack will be the first one popped out

 ### Terminology

  - *Push* - add a node to the stack **O(1)**
  - *Pop* - remove a node from a stack **O(1)**
  - *Top* - The top node of the stack
  - *Peek* - look at the top node of a stack **O(1)**
  - *isEmpty* - `true` when a stack is empty, `false` when it is not **O(1)**

  ## Stack Visualization

  Stacks are like a deck of playing cards. Each card's face denotes its value, as well as *"faces"* the single next card directly below it. The topmost card on the top of the deck is the 'top' card. The deck of cards can grow in height as new cards are added to it, but they must be placed only on top of the existing deck. In this way a card added to the deck becomes the 'top' card. Cards may also be drawn from the deck, again only from the top of the deck. When the card is taken from the deck the card directly below it becomes the new 'top' card of the deck. If the deck has any cards at all, we can *'peek'* at the (value) of the top card on the deck. And, lastly, we can determine whether or not there are any cards in the deck at anytime.

  ## What is a Queue

  ### Terminology

  - *Enqueue* - add a node/item to the queue
  - *Dequeue* - remove a node/item from the queue
  - *Front* - the first(front) node/item in the queue
  - *Rear* - the last(rear) node/item in the queue
  - *Peek* - view the value of the 'front' node of the queue
  - *IsEmpty* - `true` when a queue is empty, `false` when it is not

Stacks follow **FIFO/LILO** rules where:

  - The first node pushed/added to a queue will be the first one removed
  - The last node pushed/added to a queue will be the last one removed

  ## Queue Visualization

  Queues are like single file lines of people, all facing the front of the line, waiting their respective turns. Each person is *'next'* in line compared to the person in front of them. The join the queue by getting into the line in the rearmost position. People leave the line after reaching the front of it. When we peek at the line, if there is one at all, we can see who is in the front. We can also tell if there is a line or not.

[Back to Main](../README.md)