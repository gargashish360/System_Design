#Map-Reduce:

* When we have very large datasets, it is important to process them in parallel. Hence, at this point this concept comes into play.
* The Map part divides the data to be processed in parallel, and make up key-value pairs. These are intermediate key-value pairs.
  For Example:
  --> For Example, if you want to find "king" phrase in documents then king can be a key on those parallel machines, and their count will be the values.
* In reduce step the key-value pairs will be reduced to some final output. 
* Map and Reduce functions are idempotent. If we do map-reduce multiple times, the output will be same.
* A Shell script to run map and reduce steps accordingly.
