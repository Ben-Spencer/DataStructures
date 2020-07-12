# Stacks, Queues, and Deques

Stacks, Queues, and Deques are linear data structures that force operations to be done at the front and/or back of the list. All three data structures can be implemented as both arrays (lists in Python) and linked lists; however, each implementation has different effects on the computational complexity. <br><br>
For example, implementing a queue as a linked list would not necessarily be the best idea, as either the enQueue and deQueue function would have to traverse the entire list before inserting / removing the element. Also, linked lists use additional storage, as they store pointers along with data. 
<br><br>
In summation: queues and deques are best implemented as arrays. Stacks work best as linked lists.
<br>
| | Stacks | Queues | Deques |
|-| -----| ---| ---|
|Behavior | Last in First Out (LIFO) | First in First Out (FIFO) | Either Side in Either Side Out |
|Main Operations | isEmpty, Push, Pop, Peek, getSize | isEmpty, EnQueue, DeQueue, Peek, getSize | isEmpty, InsertFront, InsertBack, RemoveFront, RemoveBack, PeekFront, PeekBack, getSize | 
| Data Structure | Array, Linked List | Array, Linked List | Array, Linked List |

<h3>Array Stack Implementation</h3>
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
 
 <h3>Linked List Stack Implementation</h3>
 <br>
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

<h3>Array Queue Implementation</h3>
<pre>
class ArrayQueue:<br>
  def __init__(self):<br>
    self.items = []<br>
  def isEmpty(self):<br>
    return self.items == []<br>
  def enQueue(self, item):<br>
    self.items.append(item)<br>
  def deQueue(self):<br>
    return self.items.pop(0)<br>
  def peek(self):<br>
    return self.items[0]<br>
  def getSize(self):<br>
    return len(self.items)<br>
  def __str__(self):<br>
    return str(self.items)
</pre>

<h3>Linked List Queue Implementation</h3>
 <br>
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
class LinkedListQueue:<br>
  def __init__(self):<br>
    self.head = None<br>
  def isEmpty(self):<br>
    return self.head == None<br>
  def enQueue(self, item):<br>
    new_node = Node(item)<br>
    new_node.setNext(self.head)<br>
    self.head = new_node<br>
  def deQueue(self):<br>
    current = self.head<br>
    prev = None
    while current.getNext():<br>
      prev = current<br>
      current = current.getNext()<br>
    popped_node = current<br>
    prev.setNext(None)
    popped_node.setNext(None)
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

<h3>Array Deque Implementation</h3>
<pre>
class ArrayDeque:<br>
  def __init__(self):<br>
    self.items = []<br>
  def isEmpty(self):<br>
    return self.items == []<br>
  def insertFront(self, item):<br>
    self.items.insert(0, item)<br>
  def insertBack(self, item):<br>
    self.items.append(item)<br>
  def removeFront(self):<br>
    return self.items.pop(0)<br>
  def removeBack(self):<br>
    return self.items.pop()<br>
  def peekFront(self):<br>
    return self.items[0]<br>
  def peekBack(self):<br>
    return self.items[0]<br>
  def getSize(self):<br>
    return len(self.items)<br>
  def __str__(self):<br>
    return str(self.items)
</pre>

<h3>Linked List Deque Implementation</h3>
 <br>
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
class LinkedListDeque:<br>
  def __init__(self):<br>
    self.head = None<br>
  def isEmpty(self):<br>
    return self.head == None<br>
  def insertFront(self, item):<br>
    new_node = Node(item)<br>
    new_node.setNext(self.head)<br>
    self.head = new_node<br>
  def insertBack(self, item):<br>
    new_node = Node(item)<br>
    current = self.head<br>
    if current:<br>
      while current.getNext():<br>
        current = current.getNext()<br>
      current.setNext(new_node)<br>
    else:<br>
      self.head = new_node<br>
  def removeFront(self):<br>
    popped_item = self.head<br>
    popped_item.getNext() = self.head<br>
    popped_item.setNext(None)<br>
    return popped_item<br>
  def removeBack(self):<br>
    current = self.head<br>
    prev = None<br>
    while current.getNext():<br>
      prev = current<br>
      current = current.getNext()<br>
    popped_node = current<br>
    prev.setNext(None)<br>
    popped_node.setNext(None)<br>
    return popped_node.getData()<br>
  def peekFront(self):<br>
    return self.head.getData()<br>
  def peekBack(self):<br>
    current = self.head<br>
    while current.getNext():<br>
      current = current.getNext()<br>
    return current.getData()<br>
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
