<h1>Linear Data Structures</h1>
Linear data structures share the following properties:<br>
* Data elements are sequentially connected and each element is traversable in a single run<br>
* All elements are on one single level, rather than multi-level (such as trees)<br>
* Generally, do not use memory efficiently<br>
* Time complexity is normally at least O(n). There are exceptions, such as binary search.<br>
<h2>Comparison Between Linear Data Structures</h2>

| | Arrays | Lists |
|-| ------ | ----- |
|Memory Access | Random Access Memory (through indexing) | Sequential Memory Access |
| Append | Constant Complexity | Linear Complexity |
| Insertion / Deletion | Linear Complexity | Constant Complexity |
| Traversal | Constant Complexity | Linear Complexity |
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
<h2>Linked List Implementation</h2>
<pre>

</pre>

