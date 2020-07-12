<h1>Linear Data Structures</h1>
Linear data structures share the following properties:<br>
* Data elements are sequentially connected and each element is traversable in a single run<br>
* All elements are on one single level, rather than multi-level (such as trees)<br>
* Generally, do not use memory efficiently<br>
* Time complexity is normally at least O(n). There are exceptions, such as binary search.<br>
<h2>Comparison of Linear Data Structures</h2>

| | Arrays | Lists |
|-| ------ | ----- |
|Memory Access | Random Access Memory (through indexing) | Sequential Memory Access |
| Append | Amortized O(1) | O(n) due to Traversal |
| Prepend | O(n) | O(1) |
| Insertion / Deletion | O(n) | O(1) |
| Traversal | O(n) | O(n) |
| Search | Binary Search [O(log n)] | Linear Search [O(n)]
| Memory Size | Fixed | Dynamic |
| Storage Type | Consecutive | Random |
| Data Cost | Less [Only data is stored] | More [Pointer(s) are stored, as well as data] |
| Memory Utilization | Inefficient (due to fixed memory) | Efficient (due to dynamic memory) |

<br>
<h2>Array Implementation</h2>
<pre>
class Array:
  def __init__(self):
    self.arr = []
  def append(self, item):
    self.arr.append(item)
  def prepend(self, item):
    self.arr.insert(0, item)
  def __str__(self):
    return str(self.arr)
</pre>
<br>

<h2>Types of Linked Lists</h2>
  
|  | Singly Linked List | Doubly Linked List | Circular Linked List | Doubly Circular Linked List |
|--| ------------------ | ------------------ | -------------------- | --------------------------- |
| Implementation | Node contains data and a pointer to next node. | Node contains data and a pointer to next and previous nodes. | Node contains data and a pointer to next node. Last node has a pointer to head node. | Node contains data and a pointer to next and pervious nodes. Last node has a pointer to head node. |
| Order of Elements | Allows traversal in one direction. Set head node. | Allows traversal in two directions. Set head node. | Allows traversal in one direction. Any node can be head. | Allows traversal in two directions. Any node can be head.|
| Usage | Implementing stack data structure. | Implementing deque data structure. | Implementing fibonacci heaps. |  Implementing two-direction fibonacci heaps. | 





<h2>Singly Linked List Implementation</h2>
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
class SinglyLinkedList:<br>
    def __init__(self):<br>
        self.head = None<br>
    def isEmpty(self):<br>
        return self.head == None<br>
    def prepend(self,item):<br>
        temp = Node(item)<br>
        temp.setNext(self.head)<br>
        self.head = temp<br>
    def append(self, item):<br>
        temp = Node(item)<br>
        current = self.head<br>
        if current:<br>
            while current.getNext() != None:<br>
                current = current.getNext()<br>
            current.setNext(temp)<br>
        else:<br>
            self.head = temp<br>
    def size(self):<br>
        current = self.head<br>
        count = 0<br>
        while current != None:<br>
            count = count + 1<br>
            current = current.getNext()<br>
        return count<br>
    def removeBackHalf(self):<br>
        ls = self.listSize()<br>
        mid = ls//2<br>
        current = self.head<br>
        count = 1<br>
        while count < mid:<br>
            count += 1<br>
            current = current.getNext()<br>
        current.setNext(None)<br>
    def search(self,item):<br>
        current = self.head<br>
        found = False<br>
        while current != None and found != True:<br>
            if current.getData() == item:<br>
                found = True<br>
            else:<br>
                current = current.getNext()<br>
        return found<br>
    def reverse(self):<br>
        prev = None<br>
        current = self.head<br>
        while current:<br>
            next = current.getNext()<br>
            current.setNext(prev)<br>
            prev = current<br>
            current = next<br>
        self.head = prev<br>
    def remove(self,item):<br>
        current = self.head<br>
        previous = None<br>
        found = False<br>
        while found != True:<br>
            if current.getData() == item:<br>
                found = True<br>
            else:<br>
                previous = current<br>
                current = current.getNext()<br>
        if previous == None:<br>
            self.head = current.getNext()<br>
        else:<br>
            previous.setNext(current.getNext())<br>
    def sortedMerge(self, a, b): <br>
        result = None<br>
        if a == None: <br>
            return b <br>
        if b == None: <br>
            return a <br>
        if a.getData() <= b.getData():<br>
            result = a <br>
            result.setNext(self.sortedMerge(a.getNext(), b))<br> 
        else: <br>
            result = b <br>
            result.setNext(self.sortedMerge(a, b.getNext()))<br>
        return result <br>
    def mergeSort(self, h): <br>
        if h or h.getNext(): <br>
            return h<br>
        middle = self.getMiddle(h) <br>
        nexttomiddle = middle.getNext()<br>
        middle.setNext(None)<br>
        left = self.mergeSort(h) <br>
        right = self.mergeSort(nexttomiddle) <br>
        sortedlist = self.sortedMerge(left, right) <br>
        return sortedlist<br>
    def getMiddle(self, head): <br>
        if (head == None): <br>
            return head <br>
        slow = head <br>
        fast = head <br>
        while fast.getNext() and fast.getNext().getNext(): <br>
            slow = slow.getNext()<br>
            fast = fast.getNext().getNext()<br>
        return slow<br>
    def printList(self):<br>
        current = self.head<br>
        s = ""<br>
        while current:<br>
            s = s + str(current.getData()) + " -> "<br>
            current = current.getNext()<br>
        s = s + "None"<br>
        return s
</pre>
<h2>Doubly Linked List Implementation</h2>
<pre>
class Node:
	def __init__(self, initdata):
		self.data = initdata
		self.next = None
		self.prev = None
	def getData(self):
		return self.data
	def getNext(self):
		return self.next
	def getPrev(self):
		return self.prev
	def setData(self, newData):
		self.data = newData
	def setNext(self, newNext):
		self.next = newNext
	def setPrev(self,newPrev):
		self.prev = newPrev

class DoublyLinkedList:
	def __init__(self):
		self.head = None
	def isEmpty(self):
		return self.head == None
	def prepend(self, data):
		new_node = Node(data)
		new_node.setNext(self.head)
		new_node.setPrev(None)
		self.head = new_node
	def append(self, data):
		new_node = Node(data)
		if current:
			while current.getNext():
				current = current.getNext()
			current.setNext(new_node)
			new_node.setPrev(current)
			new_node.setNext(None)
		else:
			self.head = new_node
			new_node.setPrev(None)
	def addAfterTarget(self, target, data):
		new_node = Node(data)
		current = self.head
		while current.getData() != target:
			current = current.getNext()
		new_node.setPrev(current)
		new_node.setNext(current.getNext())
		current.setNext(new_node)
		current.getNext().setPrev(new_node)
	def removeTarget(self, target):
		current = self.head
		prev = None
		while current.getData() != target:
			prev = current
			current = current.getNext()
		removed_item = current
		prev.setNext(current.getNext())
		removed_item.setNext(None)
		return removed_item.getData()
	def __str__(self):
		s = ""
		current = self.head
		while current:
			s = s + str(current.getData()) + " <-> "
			current = current.getNext()
		return "None <-> " + s + "None" 
</pre>
 
