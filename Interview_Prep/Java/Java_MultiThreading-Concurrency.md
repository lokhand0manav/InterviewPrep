## Java MultiThreading and Concurrency
- Ref : http://codinglords.com/blog/getById/61
- wait() vs sleep()
	- sleep() is static method in Thread class, wait is instance in Object class
	- sleep() doesnt require synchronous block as it doesnt release the lock it holds
	- wait releases the lock it holds an hence requires a synchronous block