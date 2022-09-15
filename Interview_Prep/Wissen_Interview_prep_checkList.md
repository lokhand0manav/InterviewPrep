## Wissen Interview
1) Can one use an Employee class as a key in a HashMap? (This is a very important question. Please cover this in depth)
	- Evaluation Parameter- overriding hashCode ,overriding equals ,the behavior if hashCode returns a constant (including get and put time complexity), 
	- the behavior if hashCode is not imlemented but equals is .
2) You are using a class from a library (say Student). You have a list of Student objects. You need to sort this list based on first name. How will you do it? 
	- Constraint: (You do not have the ability to change the source code of the Student class) 
3) Consider a class Person with two attributes - String name and `List<String>` degrees. How will you make this class immutable. Ask what are the advantanges of immutable classes
	- Evaluation Parameter- 
		- Make all fields private and final,
		- Remove the setter methods, 
		- Return either a new copy of degrees (deep copy) or an unmodifiableList in the the getter method, 
		- In the constructor, make a copy of the List argument passed, 
		- Make the class final, 
		- Knows the benefits of immutable class in multi-threaded programs and as a good design practice.
		- #### Ref : http://codinglords.com/blog/get/immutability-and-thread-safety-in-java
4) Consider a class A with a synchronized method
	`class A {`
		
			public void synchronized m1() {Thread.sleep(5000);}
		}
	`public class MainClass{`
		
		public static void main(String args[]){	
			A o1 = new A(); 
			A o2 = new A(); 
	
			Thread t1 = new Thread(()->{ o1.methodA();});  
			Thread t2 = new Thread(()->{ o2.methodA();});  
			t1.start();  
			t2.start();
		}
	`}`
	- We create two objects of this class - o1 and o2. We call o1.m1() on one thread and o2.m1() on another thread, at the same time. What will be the behaviour?
	- Follow up with - how will you force these calls to execute one after the other
		- `t1.join()` <-- this will make main thread wait until t1 is finished. and then you can call `t2.start` which will make main method start t2
	- Understands object level synchronization. These two calls do not block each other.
	- Suggests a solution using a shared lock object or class level synchronization.
5) We have a Parent class with 2 methods walk and run. We have a child class which overrides both the methods. Both child class methods just call their respective Super implementation.
  Parent class run method calls walk().
	`class Parent{` 
	    
	    public void walk(){  
	        System.out.println("Parent Walk");  
	    }  
	    public void run(){  
	        walk();  
	    }  
	`}`  
	`class Child extends Parent{  `
	    
	    public void walk(){  
	        super.walk();  
	    }  
	    public void run(){  
	        super.run();  
	    }  
	`}`
	`class Test {  `
	    
	    public static void main(String[] fun) {  
	        Parent p = new Child();  
	        p.run();  
	    }  
	`}`
	Tell the order in which each method is called
	- Correctly tells the order: child.run -> parent.run -> child.walk -> parent.walk.
6) Given a List of integers (`List<Integer>`), write code in Java 8 style to get the sum of the squares of all the odd numbers in the array.
	- Evaluation Parameter
	1. Used stream() correctly.
	2. Used filter() correctly.
	3. Used map() correctly.
	4. Used sum() or reduce() correctly.
7) What is the difference between `HashMap` and `ConcurrentHashMap`? Follow up with - what is the difference between `ConcurrentHashMap` and `synchronizedMap()`.
	1. Knows that `ConcurrentHashMap` is thread-safe.	
	2. Knows about `ConcurrentModificationException`.
	3. Knows how `ConcurrentHashMap` allows concurrent read and write as opposed to `synchronizedMap()`.
	4. Knows how read operation does not take a lock and still is thread safe.
8) Explain what the following command does on Unix:
	chmod 764 file1
	 r4w2x1 (Alphabetical order with x =1)
	 oge ( ulta alphabetical )
 	1. Knows that this command changes the access permissions on the file..	
	2. Can explain the meaning of 764 - read,write and execute permission for the owner, read and write permission for the group and read permission for everyone.
9) We have a table called BookAuthor. It has two columns Book and Author, Book being unique column.
	- Write a query to find the names of the authors who have written more than 10 books.

	select athrs from bathrs  group by athrs having count(athrs)>10
	
	1. Knows the usage of group by.
	2. Knows the usage of count(*).
	3. Knows the usage of having.
	4. Knows that the "where" clause does not work in this case
10) Given an array of n integers and a number k, find the pairs of numbers in the array such that the difference between the pair is k. Find the optimal solution with and without extra storage
	1. Gave O(n) solution with extra storage by using HashMap.
	2. Gave O(n log n) solution without extra storage by using sorting.
	3. If the array is sorted, is able to give O(n) solution by using iteration with 2 pointers.
11) Delete PK without FK  
    (Cascade in Database)
12) print hello world without using ";"
    - use IF statement
    - Will not work normal println, need **printf** (Something that returns some value)
13) DateTime Api methods
	(before and after)
	- Ref : https://www.tutorialspoint.com/java8/java8_datetime_api.htm
14) GC collector vs your own new Garbage collector	
15) New Functionality for hashmap when collision happens and large list is formed
    It is converted to BST
16) HashSet vs TreeSet - use & benfits



--------------------------------------------round 2--------------------------------------------


1) Linkedlist internals
2) Binary tree internals
3) Linked hashmap implementation
4) Books-authors  -- Many to many table design
5) Method overriding rules
    - In java, a method can only be written in Subclass, not in same class.
    - The argument list should be exactly the same as that of the overridden method.
    - The return type should be the same or a subtype of the return type declared in the original overridden method in the super class.
    - The access level cannot be more restrictive than the overridden method’s access level.
	    - For example: if the super class method is declared public then the over-ridding method in the sub class cannot be either private or protected.
    - Instance methods can be overridden only if they are inherited by the subclass.
    - A method declared final cannot be overridden.
    - A method declared static cannot be overridden but can be re-declared.
    - If a method cannot be inherited then it cannot be overridden.
    - A subclass within the same package as the instance’s superclass can override any superclass method that is not declared private or final.
    - A subclass in a different package can only override the non-final methods declared public or protected.
    - An overriding method **can throw any uncheck exceptions**, regardless of whether the overridden method throws exceptions or not.
    - However the overriding method should not throw checked exceptions that are new or broader than the ones declared by the overridden method. 
	    - The overriding method can throw narrower or fewer exceptions than the overridden method.
    - Constructors cannot be overridden.
6) 12 balls of same color ,among them one is of different weight, given a classic weighing machine , find out the odd ball
7) Flood Fill Algorithm
	- This is some graph releated algorithm, till the border is not filled fill them
1) 2 threads each printing numbers in order 1, 2, 3...
    Design synchronization code such that Thread A never prints a number higher than the most recent number printed by Thread B (Thread A is always behind Thread B)

9) There is a csv file with the following data
    share name, price, buy/sell, quantity, time
    This stores transaction data for one day.

    You have to parse and store it in a data structure.
    Which data structure would be best for each scenario/queries

    1. Find number for trades each stock had
    2. Find the max value a stock traded at
    3. Find the max value a stock trades at within a time range

10) class A {
    }

    Add some logic to class A such that any class that extends it can only be instantiated once.

11) Implement a new List that implements all the functions of a list interface.
    The underlying implementation can be determined by the user (like the user can say he wants the underlying implementation to be ArrayList, Linked list, etc)
    The only difference is our implementation should track number of times add or addAll methods are called.


----------------------Some more -------------------------------------------------------------
1. Databases / SQL -RDBMS concepts, txn consistency/isolation levels, Optimistic vs Pessimistic lock, partition vs index usage + writing SQL queries+NoSQL
2. Problem Solving-Sliding Window - Binary search & linked list based problem  + Palindrome + low and high index from the list of sorted integers-O(logn) Solution with constant space complexity
3. Query to fetch department wise  employee record having max salary
4. Write a program get dates in range as List of string for following dates
	- Dates strings :  '2021-01-01' and '2021-01-31' 
5. For a  sorted array, write a program to get min and max index for a seach value
6. Then a coding question Given an array of sorted integers and a target number Find target in array
7. Data Structures-queue and stack , enqueue and dequeue
8. Multithreading - Optimized approach of o{n} complexity What is exception handling Multithreading Toughest challenge faced in a project...
9. Java Collections-trade offs and internal working.
10. OOPs-Concepts
11. SQL-Given employee table find employees who earn highest salary in their respective department s
12. txn management, cache, partitions and indexes.
13.  write a group by query.
14. Given an array of sorted integers and a target number Find the start index of target number and endIndex of target Number
  
- Refresher (Java, Spring Boot, Databases)
	- Basics of Core java
	- Exception handling.
		- Checked exception vs unchecked exception
		- Overriding the methods which throws checked or unchecked exceptions
	- Generics
	- Serialization
	- OOPs concepts
	- Immutable class
	- Abstract class and interfaces
	- Encapsulation vs Abstraction
- Data structures / Java Collections
	- Internals of HashMap, HashSet, TreeMap, TreeSet, LinkedList
	- LRU cache implementation (Hint LinkedHashMap)
	- Why there is a hash method inside the HashMap class?  
		- (Hint: It’s not for key.hashcode() % bucket_size)
	- Uses of loadfactor and treefy threashold.
	- an HashSet contain a duplicate value?
		- (Yes, it can when equals and hashcode methods don’t follow the contract)
		- Find out what is the contract between them?
	- Time complexity of all the operations on HashMap, HashSet, TreeMap, TreeSet, Stack and Queue for Best case, worst case and average case.
- SQL, DB2, Stored Procedures
	- Find the most recently hired emps in each department.
    [https://www.w3resource.com/sql-exercises/employee-database-exercise/sql-subqueries-exercise-employee-database-52.php](https://www.w3resource.com/sql-exercises/employee-database-exercise/sql-subqueries-exercise-employee-database-52.php)

Follow up:  

       Can you optimize it further if we are fetching data in batches?

       Can you solve it using proprietary functions like row_number()

- Practice joins
	- [https://www.w3resource.com/sql/joins/sql-joins.php](https://www.w3resource.com/sql/joins/sql-joins.php)
- Write a query in SQL to list the details of the departments where maximum number of employees are working.
-   Write a query in SQL to find one employee from each department who is getting the highest salary within his department. (Don’t forget to handle corner case where multiple / no employees are getting highest salary in a department.)
-   Write a query in SQL to list the details of the departments where maximum number of employees are working. (1 department with max employee or multiple departments having same number of employees)
    
- Microservices using spring webmvc, spring boot
	- What is the use of service registry and discovery?
	- Get familiar with usage of zookeeper, eureka and consul as a service discovery. Added advantage if you know trade off of all these solutions.
	- What are the key benefits of using Spring Boot?
	- Auto Configuration
	- Dependency management using starter parent
	- Actuator and Health Checks
	- Embedded Web Server
	- How to implement Fault tolerance and circuit breaker?
	- CAP theorem.
	- What is the role of API Gateway in microservice architecture?
	- How do you decide that a microservice should expose HTTP or JMS listener?
	- Microservices design patterns specially SAGA patterns, API Composition pattern and CQRS pattern
- Spring Framework
	- AOP concepts like Join point, Advice etc.
    
- Problem Solving
	1. Implement a queue using stacks. Prepare for follow up questions also.
	2. Find first and last positions of an element in a sorted array. (Observe the pattern like here array is sorted and it may contain duplicates)
	    [https://www.geeksforgeeks.org/find-first-and-last-positions-of-an-element-in-a-sorted-array/](https://www.geeksforgeeks.org/find-first-and-last-positions-of-an-element-in-a-sorted-array/)
	3. Detect and Remove Loop in a Linked List.
		 - [https://www.geeksforgeeks.org/detect-and-remove-loop-in-a-linked-list/](https://www.geeksforgeeks.org/detect-and-remove-loop-in-a-linked-list/)
	4. Add two numbers represented by linked lists.
	5. Inorder Tree Traversal without Recursion.
	6. How to design an LRU cache. Which data structure you would like to use?
		- Hint: LinkedHashMap Or HashMap + LinkedList
	7. Find the k most frequent words from a file.
		- [https://www.geeksforgeeks.org/find-the-k-most-frequent-words-from-a-file/](https://www.geeksforgeeks.org/find-the-k-most-frequent-words-from-a-file/)
	8. Print N’th node from the end of a Linked List.
		- [https://www.geeksforgeeks.org/nth-node-from-the-end-of-a-linked-list/](https://www.geeksforgeeks.org/nth-node-from-the-end-of-a-linked-list/)
	1. Find K largest (or smallest) elements in an array.
		- There are multiple ways to solve this but using Min/max heap is the better solution.[https://www.geeksforgeeks.org/k-largestor-smallest-elements-in-an-array/](https://www.geeksforgeeks.org/k-largestor-smallest-elements-in-an-array/)

- Algorithms
	- Timsort (Used by Java for objects)
	- Quick Sort (Double Pivot Quick Sort is used by Java for primitives)
	- Merge sort

- Multithreading / Concurrency
	- Intrinsic and extrinsic locks
	- How wait() and notify() works internally?
	- Spurious wakeup and SpinLock
	- Synchronization puzzle like print 1 to N sequentially from 2 threads one should be printing even numbers and one should be printing odd numbers.
	- Deadlock prevention techniques
	- When we should prefer volatile int/long over the Atomic Integer / Atomic Long?
	- When we should prefer Atomic Integer / Atomic Long over the intrinsic and extrinsic locks?
	- How to Design a website visitor counter. Come up with at least 3 solutions and be aware about the pros and cons of each one. 
	- Get Familiar with Semaphores, CountDownLatch and CyclicBarrier.
	    [https://www.baeldung.com/java-semaphore](https://www.baeldung.com/java-semaphore)
		[https://www.baeldung.com/java-cyclicbarrier-countdownlatch](https://www.baeldung.com/java-cyclicbarrier-countdownlatch)
	- Assume you have to replace the thread pool of any web application server using your custom thread pool executor. Try to build it and submit some tasks to it.
		- Do load testing of the same.
		[https://howtodoinjava.com/java/multi-threading/java-thread-pool-executor-example/](https://howtodoinjava.com/java/multi-threading/java-thread-pool-executor-example/)
	- Get familiar with class level and object level locks.
		- [https://howtodoinjava.com/java/multi-threading/object-vs-class-level-locking/](https://howtodoinjava.com/java/multi-threading/object-vs-class-level-locking/)

- Design Principles / Patterns
	- SOLID Design Principles
		- Real world use cases, good to relate it with the work you have done
	- Singleton Design pattern <-- Creational
	- Java vs Spring IOC, how to break it? 
	- Strategy Design Pattern <-- Behavior
	- Decorator Design Pattern <-- Structural
	- Adaptor Design Pattern <-- Structural
	- Builder Design Pattern <-- Creational
	- Observer Design Pattern <-- Behavior
	- Template Design Pattern<-- Behavior
- JVM Internals
	- Diagnose Out of memory error. 
	- Heap dumps, memory dumps