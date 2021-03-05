# Trees - How Depth First Traversal Works
---

## Terminology

- *Node* - a component ofa tree that contains its own value and reference(s) to other nodes
- *Root* - The node at the beginning of a tree
- *Left* - in a binary tree, references one of the two child nodes to a node
- *Right* - in binary trees, references the other of the two child nodes

## Explanation of Traversing Trees using Depth First

**Recursion** is the most common method of tree traversal and utilizes a *call stack*. There are **three** methods for depth first traversal. They are:
- Pre-Order
- In-order
- Post-Order

![Sample Tree](./tree-sample.png)


### Pre-order - `root` -> `left` -> `right`

1. Determine starting node and make it the `current` node
1. Output `current` value
1. Check for an ***unused*** `left` child of the `current` node
1. If found, push `current` to stack then make child the `current` node and go back to 2
1. If not found, check for an ***unused*** `right` child of the `current` node
1. If found, push `current` to stack then make child the `current` node and go back to 2
1. Check to see if there are any nodes remaining in the stack
1. If there are, make the node now on top of the stack `current` node, pop the node off of the stack and go back to 2
1. If there are not, the traversal is complete

*Output from example tree:* 
- `A` -> `B` -> `D` -> `E` -> `C` -> `F`

### In-Order - `left` -> `root` -> `right`

1. Determine starting node and make it the `current` node
1. Check for an ***unused*** `left` child of the `current` node
1. If found, push `current` to stack and make child the `current` node and go back to 2
1. If not found, output `current` value
1. Check for an ***unused*** `right` child of the `current` node
1. If found, push `current` to stack and make child the `current` node and go back to 2
1. Check to see if there are any nodes remaining in the stack
1. If there are, make the node now on top of the stack `current` node, pop the node off of the stack and go back to 2
1. If there are not, the traversal is complete

*Output from example tree:* 
- `D` -> `B` -> `E` -> `A` -> `F` -> `C`

### Post-Order - `left` -> `right` -> `root`

1. Determine starting node and make it the `current` node
1. Check for an ***unused*** `left` child of the `current` node
1. If found, push `current` to stack then make child the `current` node and go back to 2
1. If not found, check for an ***unused*** `right` child of the `current` node
1. If found, push `current` to stack then make child the `current` node and go back to 2
1. If not found, output `current` value
1. Check to see if there are any nodes remaining in the stack
1. If there are, make the node now on top of the stack `current` node, pop the node off of the stack and go back to 2
1. If there are not, the traversal is complete

*Output from example tree:* 
- `D` -> `E` -> `B` -> `F` -> `C` -> `A`


[Back to Main](../README.md)