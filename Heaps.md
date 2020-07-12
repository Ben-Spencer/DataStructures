# Heaps
Heaps are implemented the same way as arrays. The benefit of storing a heap as an array, rather than a pointer-basaed binary tree is the following:</br>
* Lower memory usage (only store data, rather than 3 additional pointers)</br>
* Easier memory management (just one object elemented, rather than N)</br>
* Better locality of memory (heap memory is contiguous due to array implementation; if binary tree is used, memory is scattered)</br>

| Operation | Binary | Binomial | Fibonacci | Pairing | Brodal | Rank Pairing | Strict Fibonacci |
| --------- | ------ | -------- | --------- | ------- | ------ | ------------ | ---------------- |
| Find-Min | O(1) | O(log n) | O(1) | O(1) | O(1) | O(1) | O(1) |
| Delete-Min | O(log n) | O(log n) | O(log n) | O(log n) | O(log n) | O(log n) | O(log n) |
| Insert | O(log n) | O(1) | O(1) | O(1) | O(1) | O(1) | O(1) |
| Decrease Key | O(log n) | O(log n) | O(1) | O(log n) | O(1) | O(1) | O(1) |
| Merge | O(n) | O(log n) | O(1) | O(1) | O(1) | O(1) | O(1) |
