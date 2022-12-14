- ## JD :
	- Java, 
	- Databases, 
	- Middleware (Soap/Xml/Messaging/RESTful services).
	- Object Oriented Analysis, 
	- Design and Programming, **familiarity with Design Patterns**
	- multithreaded systems
- ## 3 technical Rounds and 1 Managerial Round
- Problem Solving Prep: Ref : https://www.ambitionbox.com/interviews/morgan-stanley-interview-questions/software-developer?sort_by=latest
	- Learning Binary Search
	- sum of last 10 nodes of linked list then write unit test then about complexity of algorithm
		- *Using Stream API done*
	- Design algorithm to convert hexadecimal numbers to decimal number
		- Hexadecimal are in chunks of **4 binary bits**. so AB => 1010 1011 <-- binary of AB
	- design linked list in JAVA
		- Did in java, was using a inner class for ListNodes
	- write code for producer consumer problem
		- Did in Java
	- write code to print even odd in sequence using MultiThreading
		- Did used producer consumer synchronization thingy
	- find intersection node of two linkedlist
		- Hashmap
	- find all the cousins of the node in BST
		- 
	- Implement stack using Queue
		- Using 2 queues 
		- ref : https://www.geeksforgeeks.org/implement-stack-using-queue/
	- print the number in english words for ex;4563 should be printed as "four thousand six hundred three.
	- What is heap sort, insertion sort & selection sort?
		- HeapSort:
			- Heapify in every loop, the loop goes on for **n**, while heapify(Once already heapified) takes **o(logn)** so **nlogn**
			- Ref: https://www.programiz.com/dsa/heap-sort#:~:text=Heap%20Sort%20has%20O(nlog,case%2C%20and%20worst%20case).
	- Print Binary tree in spiral order
		- 
	- Given mapping between city to city, print complete path from source city till destination city.
	- There are number of 1’s and 0’s in a 2D matrix, you have to find the max square in 2D matrix which has boundary as 1’s
	- [There are infinite number of a stream. You have to find the median at any point of time.](https://practice.geeksforgeeks.org/problems/find-median-in-a-stream/0)
		- Used 2 heaps, one max and another min. So 2 heaps used. left will be a max heap and right will be the min heap. so head of both the heaps will provide the median(middle values)
	- Find Duplicate: You have been given an integer array/list(ARR) of size N, which contains numbers from 0 to (N - 2). Each number is present at least once. That is, if N = 5, the array/list constitutes values ranging from 0 to 3 and among these, there is a single integer value that is present twice. You need to find and return that duplicate number present in the array.
	- Shortest path in an unweighted graph, The city of Ninjaland is analogous to the unweighted graph. The city has ‘N’ houses numbered from 1 to ‘N’ respectively and are connected by M bidirectional roads. If a road is connecting two houses ‘X’ and ‘Y’ which means you can go from ‘X’ to ‘Y’ or ‘Y’ to ‘X’. It is guaranteed that you can reach any house from any other house via some combination of roads. Two houses are directly connected by at max one road. A path between house ‘S’ to house ‘T’ is defined as a sequence of vertices from ‘S’ to ‘T’. Where starting house is ‘S’ and the ending house is ‘T’ and there is a road connecting two consecutive houses. Basically, the path looks like this: (S , h1 , h2 , h3 , ... T). you have to find the shortest path from ‘S’ to ‘T’.
	- You have been given an array, you have to partition negative values and positive values in that array. Negatives should be on left and positive should be on right side, order doesnt matter.
		- I have used to 2, pointers. left pointer will make sure I have negatives on left partition. and right will make sure I have positives on right partions. IF they find counter values for their respective tasks, both of them at the same time, then we will swap the numbers
- Java Language Questions:
	- How ConcurrentHash Map works
	- Blocking queue implementation
	- describe your understanding in hashcode() and equal().
	- Differnce among hashmap, concuurent hash map and synchronised map.\
	- Atomic operations
	- what is a serialversionuid and why should i use it
		- Associated to Serialized Class. It is like a checksum, to check if both the sender and receiver class are same 
	- Garbage Collection
	- Memory Leaks
	- how do you handle if in production if you got outofmemory error
- System Design:
	- Design Vending Machine
	- Buy/ Sale Stock - Find the day when you will have the max profit.
	- if you get 1000 requests for you api developed, but your hardware can handle only 200 then how can you handle load?
	- Design connection pooling,
	- Design your own load balancer
- Design Pattern:
	- What are the design patterns and how to create singleton class.
	- How to prevent Singleton Pattern from Reflection, Serialization and Cloning?
	- Thread safety in singleton