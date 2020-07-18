<h1>Preface</h1>
The lectures are available at the following links:
<ul>
 <li><a href="https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/">Introduction to Computer Science and Programming in Python</a></li>
 <li><a href="https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0002-introduction-to-computational-thinking-and-data-science-fall-2016/">Introduction to Computational Thinking and Data Science</a></li>
 <li><a href="https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/">Introduction to Algorithms</a></li>
 <li>Design and Analysis of Algorithms</li>
 <li>Advanced Data Structures</li>
 <li>Artificial Intelligence</li>
 <li>Computer Systems Security</li>
 <li>Coursera</li>
 <li>Coursera</li>
</ul>
<br>
<h1>Table of Contents</h1>
<ul>
 <li>Introduction to Computer Science and Programming in Python</li>
 <ul>
  <li>Lecture 1: What is Computation?</li>
  <li>Lecture 2: Branching and Iteration</li>
  <li>Lecture 3: String Manipulation, Guess and Check, Approximations, Bisection</li>
  <li>Lecture 4: Decomposition, Abstraction, and Functions</li>
  <li>Lecture 5: Tuples, Lists, Aliasing, Mutability, and Cloning</li>
  <li>Lecture 6: Recursion and Dictionaries</li>
  <li>Lecture 7: Testing, Debugging, Exceptions, and Assertions</li>
  <li>Lecture 8: Object Oriented Programming</li>
  <li>Lecture 9: Python Classes and Inheritance</li>
  <li>Lecture 10: Understanding Program Efficiency, Part 1</li>
  <li>Lecture 11: Understanding Program Efficiency, Part 2</li>
  <li>Lecture 12: Searching and Sorting</li>
 </ul>
 <li>Introduction to Computational Thinking and Data Science</li>
 <ul>
  <li>Lecture 1: Introduction, Optimization Problems</li>
  <li>Lecture 2: Optimization Problems</li>
  <li>Lecture 3: Graph-Theoretic Models</li>
  <li>Lecture 4: Stochastic Thinking</li>
  <li>Lecture 5: Random Walks</li>
  <li>Lecture 6: Monte Carlo Simulation</li>
  <li>Lecture 7: Confidence Intervals</li>
  <li>Lecture 8: Sampling and Standard Error</li>
  <li>Lecture 9: Understanding Experimental Data, Part 1</li>
  <li>Lecture 10: Understanding Experimental Data, Part 2</li>
  <li>Lecture 11: Introduction to Machine Learning</li>
  <li>Lecture 12: Clustering</li>
  <li>Lecture 13: Classification</li>
  <li>Lecture 14: Classification and Statistical Sins</li>
  <li>Lecture 15: Statistical Sins and Wrap-Up</li>
 </ul>
 <li>Introduction to Algorithms</li>
 <li>Design and Analysis of Algorithms</li>
 <li>Advanced Data Structures</li>
 <li>Artificial Intelligence</li>
 <li>Computer Systems Security</li>
 <li>Coursera</li>
 <li>Coursera</li>
</ul>
 
<h1>Introduction to Computer Science and Programming in Python</h1>
<h2>Lecture 1: What is Computation?</h2>
<p>Computers perform built-in and programmer-defined calculations and store results.<br>
Types of Knowledge: Declarative (statement of fact) and Imperative (sequence of steps)<br>
An algorithm is a sequence of steps with a flow of control and a determined stopping point<br>
Basic Machine Architecture: Memory, ALU (primitive operations), Control Unit, Input / Output<br>
Anything computable in one language is computable in every other language<br>
Scalar Object: int, float, complex, bool, bytes, NoneType<br>
Non-Scalar Object: strings, lists, tuples, dictionaries, sets, and user defined classes<br>
You can use type() to find what type the object is. This is helpful in debugging<br></p>
<h2>Lecture 2</h2>


<h1>Introduction to Algorithms</h1>
<h2>Lecture 10: Open Addressing, Cryptographic Hashing</h2>
Open addressing, the simplest way to create a hash table, implements a hash table using a single array, rather than chaining with linked lists. However, to get open addressing hash tables to be efficient, you have to be more careful than when making hash tables with chaining.<br>

<h3>Open Addressing</h3>
<ul>
 <li>Open addressing is a way to implement hash tables without using chaining to deal with collisions</li>
 <li>Open addressing stores keys and values in a single array, with at most one item per slot. This means there are no collisions, and thus no need for chaining</li>
 <ul>
  <li>To ensure no collisions will occur, M, or the number of slots, has to be greater than or equal to N, the number of items
 </ul>
 <li>To ensure the hash function does not collide with another element, open addressing uses probing. Probing alters the hash function and tests slots until it finds one that does not have another key-value pair. Probing is an iterative process</li>
 <ul>
  <li>To do probing, you need a hash function that specifies the order of slots to probe for a key (for insert, search, and delete)</li>
  <li>The hash function takes in the universe of keys (U) and the trial count. Ultimately the hash function produces a number between 0 and M-1</li>
  <li>Probing must ensure that all slots are permutations of 0, 1, ..., M-1; meaning all slots have the ability to be probed by the hash function</li>
 </ul>
 <li>Insertion: while the probing function is working the hash function looks like this: h(100,1) = 4. 100 is the value, 1 is the trial count, and 4 is the slot. If the slot of 4 is already occupied, it then becomes h(100,2) = 7. This continues until it finds an open slot (either DeleteMe or None)</li>
 <li>Search: As long as the slot probed is not equal to the key (k), keep probing until you either encounter k or find an empty slot. Since you are using the same hash probing algorithm that would be used to insert, if it returns None, k does not exist. </li>
 <ul>
  <li>Search treats DeleteMe the same as an incorrect key, instead of None. Therefore it keeps going</li>
 </ul>
 <li>Delete: If you delete an early number and replace it with None, that messes up search. Instead, delete the element, then replace it with a DeleteMe flag, that is different than None. </li>
 </ul>
 <h3>Probing Strategies</h3>
 <ul>
  <li>Linear Probing: h(k,i) = (h'(k)+i) mod M. In other words, the initial hash function is random, however, if the slot is filled, it just adds 1 to the slot until it finds an empty slot. It satisfies permutation; however, clustering occurs</li>
  <ul>
   <li>Clustering is a consecutive group of occupied slots. This is bad for load balancing, as ideally the entire array would be used, rather than just small parts. It ruins the randomness of the hashing algorithm</li>
   <li>The alpha (N/M), or load factor, is log(N) when linear probing is used. Clusters cause the hash table to be O(n) rather than O(1)</li>
 </ul>
 <li>Double Hashing: h(k,i) = (h1(k)+ih2(k)) mod M. h1 and h2 are ordinary hash functions. Double hashing works well compared to linear probing.</li>
 <ul>
  <li>If h2(k) is relatively prime to M, than it satisfies permutation</li>
 </ul>
</ul>
<h3>Uniform Hashing Assumption</h3>
<ul>
 <li>Uniform hashing assumption is that each key is equally likely to have any one of the n factorial permutations as its probe sequence</li>
 <ul><li>You can get close with double hashing, but nobody has discovered a perfect hash function to satisfy this property</li></ul>
 <li>With uniform hashing assumption, you can prove that if alpha is N/M, the cost of operations, such as search, insert, and delete is <= 1 / (1-alpha)</li>
  <li>In practice, when alpha gets to around .5, it is necessary to increase the size of M (add more slots) to ensure the cost of operations remains low. Otherwise, use a chaining table</li>
 <li>Open addressing is less expensive, in terms of memory, than chaining tables, since there is no need to use pointers</li>
</ul>
<h3>Cryptographic Hashing</h3>
<ul>
 <li>Password Storage Problem: How do you store a password with nobody knowing it, including the system's admin?</li>
 <ul>
  <li>One-Way Cryptographic Hash: given h(x) = Q --> The value of the hash, it is very hard to find x. Basically, it compares your hashed login password to the saved hash, rather than your password. If the two hashes don't match, than you can't login.</li>
 </ul>
</ul>
<br>

<h2>Lesson 11: Integer Arithmetic, Karatsuba Multiplication</h2>
