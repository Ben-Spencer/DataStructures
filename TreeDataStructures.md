<h1>Tree Data Structure</h1>
Trees are non-linear, hierarchical data structures. They are a widely used abstract data type (ADT), composed of the following:</br>
<ul>
  <li>Node: Basic unit of trees that contain data and pointers to other nodes</li>
  <li>Edges: The connection, or pointer, between a parent and child node</li>
  <li>Root Node: A node from which the rest of the tree stems. Normally depicted at the top of the tree</li>
  <li>Parent Node: A node that extends a pointer to a child node</li>
  <li>Child Node: A node that is pointed to by a parent node</li>
  <li>Sibling Node: Two or more nodes that connect to one parent node</li>
  <li>Leaf Node: A node that has no children nodes</li>
  <li>Degree: The number of children had by a node</li>
  <li>Depth: The number of edges on the path from a chosen node to the root. The root node has a depth of 0</li>
  <li>Height: The longest path from a chosen node to a leaf</li>
  <li>Forest: A set of trees</li>
</ul>
<h2>General Tree</h2>
General trees are the most basic type of tree. General trees have the following rules that differentiate them from graphs:</br>
<ul>
  <li>The root node has no parent node. There is exactly one root node</li>
  <li>Each child node has exactly one parent node. There are no cycles in trees</li>
</ul>
<h2>Binary Tree</h2>
Binary trees are different from general trees in that each parent node is restricted to having 0, 1, or 2 children nodes.</br>
