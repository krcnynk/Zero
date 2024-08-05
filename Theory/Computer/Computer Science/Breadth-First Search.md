Tags: [[Algorithms]]

- **Initialize**:
    - Create a queue and enqueue the starting node.
    - Mark the starting node as visited.
- **Process**:
    - While the queue is not empty:
        - Dequeue a node from the queue.
        - Process the node (e.g., print it, check for a condition).
        - Enqueue all adjacent (or neighboring) nodes that haven't been visited yet and mark them as visited.
- **Repeat** until the queue is empty.