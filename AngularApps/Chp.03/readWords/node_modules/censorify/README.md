----------------------
Command Line Arguments
----------------------

Example:  ./word-count -b -sort SelectionSort -suf < textfile

-------------------------
Design Decisions & Issues
-------------------------
Since we stereotype against english majors, let's avoid writing this in an
essay format...

Q.  The original BinarySearchTree::Insert() resolves key collosion by
overwriting the old value with the new value.  How does the modified insert
functions resolve key collosions?

A.  The modified insert functions resolve key collosions by adding the new
value to the old value.  For example, if there exists a key K with a value 3,
and we wanted to insert a key K with value 2, the Insert function would change
the value to 3+2=5.  For our word-count, every key is inserted with a value 1.
However, it's easy to see that the insert functions allow different changes to
be made to the existing key-value tree.
    Consequently, the + operator must be overloaded for the ValueType.  


Class Hierachy

		|-------------------------|             |------------|
                |     BinarySearchTree    |--has-a----->|   BSTNode  |
                |-------------------------|             |------------|
                           ^    ^                           ^  ^
                          /      \                          |  |
                       is-a     is-a                        |  |
                        /          \                        |  |
                       /           |--------------|         |  |
                      /            |  SplayTree   |-has-a---|  |
                     /             |--------------|            |
                    /                                        is-a 
                   /                                           |
    |----------------|                                  |------------|
    |     AVLTree    |--has-a-------------------------->| AVLNode    |
    |----------------|                                  |------------|
   


---------
Profiling
---------

Our expected performance bottlenecks for the word-count program are...

--------------------
Algorithmic Analysis
--------------------
