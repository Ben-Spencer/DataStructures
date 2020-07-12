# Stacks, Queues, and Deques

Stacks, Queues, and Deques are linear data structures that force operations to be done at the front and back of the list. All three data structures can be implemented as both arrays (lists in Python) and linked lists; however, each implementation has different effects on the computational complexity. <br><br>
For example, implementing a queue as a linked list would not necessarily be the best idea, as either the enQueue and deQueue function would have to traverse the entire list before inserting / removing the element. Also, linked lists use additional storage, as they store pointers along with data. 
<br><br>
In summation: queues and deques are best implemented as arrays. Stacks work best as linked lists.
<br>
| | Stacks | Queues | Deques |
|-| -----| ---| ---|
|Behavior | Last in First Out (LIFO) | First in First Out (FIFO) | Either Side in Either Side Out |
|Main Operations | isEmpty, Push, Pop, Peek, getSize | isEmpty, Enqueue, Dequeue, Peek, getSize | isEmpty, InsertFront, InsertBack, RemoveFront, RemoveBack, PeekFront, PeekBack, getSize | 
| Data Structure | Array, Linked List | Array, Linked List | Array, Linked List |

## Array Stack Implementation
<pre>
class ArrayStack:<br>
  def __init__(self):<br>
    self.items = []<br>
  def isEmpty(self):<br>
    return self.items == []<br>
  def push(self, item):<br>
    self.items.append(item)<br>
  def pop(self):<br>
    return self.items.pop()<br>
  def peek(self):<br>
    return self.items[-1]<br>
  def getSize(self):<br>
    return len(self.items)<br>
  def __str__(self):<br>
    return str(self.items)
 </pre>
 <br>
 ## Singly Linked List Stack Implementation
 <pre>
 class Node:<br>
  def __init__(self, initdata):<br>
    self.data = initdata<br>
    self.next = None<br>
  def getData(self):<br>
    return self.data<br>
  def getNext(self):<br>
    return self.next<br>
  def setData(self, newData):<br>
    self.data = newData<br>
  def setNext(self, newNext):<br>
    self.next = newNext<br>
<br>
class LinkedListStack:<br>
  def __init__(self):<br>
    self.head = None<br>
  def isEmpty(self):<br>
    return self.head == None<br>
  def push(self, item):<br>
    new_node = Node(item)<br>
    new_node.setNext(self.head)<br>
    self.head = new_node<br>
  def pop(self):<br>
    popped_node = self.head<br>
    self.head = self.head.getNext()<br>
    popped_node.setNext(None)<br>
    return popped_node.getData()<br>
  def peek(self):<br>
    return self.head.getData()<br>
  def getSize(self):<br>
    current = self.head<br>
    count = 0<br>
    while current:<br>
      count += 1<br>
      current = current.getNext()<br>
    return count<br>
  def __str__(self):<br>
    s = ""<br>
    current = self.head<br>
    while current.getNext():<br>
      s = s + str(current.getData()) + " -> "<br>
      current = current.getNext()<br>
    return s + "None"
    </pre>
 
