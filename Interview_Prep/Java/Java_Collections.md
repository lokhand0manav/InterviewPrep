## Java Collection:
- ![[COllectionHeirarchy.png]]
- ![[Pasted image 20220824175139.png]]
- `HashMap` is not ThreadSafe : `ConcurrentHashMap`, `synchronizedMap()` are our options
	- `ConcurrentHashMap` makes use of segment Mapping/ bucket locking. The Map is divided into various segments. No synchronisation required for retreival process. But when some thread tries to modify a segment it will take a lock on that particular segment only.
	- By default the it allows 16 threads to concurrently access the map.
	- `synchronizedMap()` method is part of 'Collections' class. This makes use of backing map (The object of a map passed as parameter) for reteival of objects. And the returned map is used for synchronisation purposes.
	- `ConucurrentModificationException` :
		- This exception is also thrown in singleThreaded environment. While iterating over a map, when trying to change , add an element, this exception will be thrown.
		- Try using iterator.remove method in for loop. Don't try in forEach loops wth an actual iterator
		- `ConcurrentHashMap` doesnt throw this exception. IF we try to modify the map while iterating.
		- `ConcurrentHashMap` doesnt allowe Null key and null values.
			- There could be many reason, but one prominent could be:
				- map.containsKey(k);
				   map.get(k);
				- https://www.reddit.com/r/java/comments/ojc7w/why_concurrenthashmap_does_not_support_null_values/ <-- read explaination here
- Set means it wont have duplicate values.
- **Lists** maintain insertion order as just adding a new entry at the end or the beginning is the fastest implementation of the add(Object ) method.
- Tree whatever means it is going to be Ordered.
	- As treeSet uses comparator for comparison it doesn't allow null object