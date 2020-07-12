# Stacks, Queues, and Deques
Stacks, Queues, and Deques are linear data structures that force operations to be done at the front and back of the list. All three data structures can be implemented as both arrays (lists in Python) and linked lists; however, each implementation has different effects on the computational complexity. <br><br>
For example, implementing a queue as a linked list would not necessarily be the best idea, as either the enQueue and deQueue function would have to traverse the entire list before inserting / removing the element. Also, linked lists use additional storage, as they store pointers along with data. 
<br><br>
In summation: queues and deques are best implemented as arrays. Stacks work best as linked lists.
<br>
| | Stacks | Queues | Deques |
|-| -----| ---| ---|
|Behavior | Last in First Out (LIFO) | First in First Out (FIFO) | Either Side in Either Side Out |
|Main Operations | isEmpty, Push, Pop, Peek, GetSize | isEmpty, Enqueue, Dequeue, Peek, GetSize | isEmpty, InsertFront, InsertBack, RemoveFront, RemoveBack, PeekFront, PeekBack, GetSize | 
| Data Structure | Array, Linked List | Array, Linked List | Array, Linked List |
