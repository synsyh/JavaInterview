# Core Java
1. What’s difference between checked exception and unchecked exception?
	* Unchecked exception occurs at runtime of the program. There are also known as runtime exception. We do not require to handle it at compile time. Checked exception occurs at compile time of the program. This exception should be caught or handled during compile time. 
	> IO related Exceptions, ClassNotFoundException, SQLException
	* Both of checked and unchecked exceptions can be handled by using catch, try and finally keywords.
	> RuntimeException and its sub exceptions classes, such as: NullPointerException, NumberFormatException, ArrayIndexOutOfBoundsException, ClassCastException
2. What the difference between exceptions and errors?
	* Both of them belong to Throwable.
	* Error: We can’t handle errors like the same way we handle exceptions. If error happens, JVM will terminate thread.
3. Difference between Interface and Abstract Class.
	* Interface can only have abstract methods. Since JDK8, it can have static and default method also. Abstract class can have abstract method and non-abstract method.
	* A class can implements multiple Interface but only one abstract class can be extended.
	* Interface only have static and final variable whereas Abstract class can have static, non-static, final, non-final variables.
	* An interface can extend another interface only. An abstract class can extend another Java class and implement multiple Java interfaces.
	* Members of Interface are public by default. An abstract class can have class members like private, protected, public and default.
4.  Throw and Throws
	* Throw is a keyword which is used to throw an exception explicitly in the program inside a function or a block of code. Throws is a keyword which is used in the method signature. This is used to declare an exception which might get thrown by a function.
	* Checked exception cannot be propagated using throw. we can only propagate unchecked exception. Throws keyword can declare both checked and unchecked exception.
	* We can not throw multiple exceptions with one throw keyword. But we can declare multiple exceptions with one throws keyword.
5. Why do we use inheritance?
	* Inheritance is a technic using exist class as basic to create a new class.
	* For code reuse.
	* Achieve polymorphism by using method overriding.
6. Difference between final, finally and finalize
	* Final: Using on variable, method and 
		* variable: It cannot change any more after its initialization.
		* Class: This class cannot be inherited by other classes.
		* Method: lock this method to prevent any inherited classes from modifying its meaning.
	* Finally: Using in try, catch block. Regardless whether the exception is caught or handled, statements in finally block will be executed. If there is return statement in catch block, statements in finally block will be executed before return statement. If catch block and finally block both have return statements, return statement in finally block will cover the return statement in catch block.
	* Finalize: It is a method that Garbage Collector always calls before the deletion of the object. It is used to perform clean-up activity. Which means closing the resources associated with that object. Like Database connection, Network connection.
7. Access Modifier
	* Public: the code is accessible for all classes
	* Private: the code is accessible for this class
	* Protected: the code is accessible for this class and subclass
	* Default: the code is accessible in same package
8. Difference between ArrayList and LinkedList.
	* Both ArrayList and Linked List are not thread safe.
	* Array list internally uses dynamic array to store element and Linked list internally uses double linked list to store element.
	* For array list, accessing a special element is O(1) time complexity but for linked list, it is O(n) time complexity.
	* For add(e) both of them are O(1) time complexity. For adding an element to a special position, array list has O(n-i) time complexity cause of all the elements after this element have to shift. But Linked list has O (n) time complexity. So array list is better for storing and accessing data, Linked list is better for manipulating data.
	* Array list wastes space because it has to reserve a certain amount of space. Linked list wastes space because it spends more space for each element.
9. How does HashMap work
	* HashMap stores key-value pairs and it uses array and linked list to store data. HashMap calculates hash code first and determines where to store in array. If this position already has an element, then compare the key and hash code. If key and hash code are both equal, then overwrite data. If not, which is called hash collision, it uses a linked list to link this element to first element.
	> And this is why we have to override hashcode() and equals()  simultaneously when we want to store our own objects into HashMap.
	* After JDK1.8, if the size of linked list is bigger than 8, the linked list will be transformed to black-red tree.
10. Difference between HashMap and HashTable
	* HashMap is not thread safe. HashTable is thread safe. Because most methods of HashTable is synchronized which means HashMap is more efficient than HashTable
	* HashMap allows one null key and multiple null values whereas HashTable doesn’t allow any null keys and values.
11. How to make HashMap thread safe?
	* Using ConcurrentHashMap
12. Difference Between List and Set
	* Elements in List is ordered (insertion order). Elements in Set is out of order.
	* List permit duplicated elements but Set does not permit duplicated elements. Each element in Set is unique.
13. Array and ArrayList
	* Array is a basic functionality provided by Java. ArrayList is part of Collection Framework. Therefore, array members can be accessed using brackets. While ArrayList has a set of methods to access elements and modify them.
	*  Array is simple fixed sized array. ArrayList is a Dynamic sized array.
	*  Array can contain both primitive data types and object of a class. However, Array List only supports object entries.
14. What is volatile?
	* Volatile is a lightweight synchronize mechanism provided by JVM. 
					1. Visibility
	        * If there is a shared variable in main memory and there are two thread want to use it. Both thread A and thread B copy the variable to their cache. When thread A change the variable with new value, thread B get this new value immediately.
		2. Not guarantee atomicity
		* Do not guarantee that all operations in one thread are executed together. When thread A complete operation and write the new value back to  main memory, thread A is blocked and thread B begin. After thread B, thread A continue write back value so we loss operation in thread B
		3. Forbid rearrangement order)
		* Make sure each statement is executed following the order we wrote. 
15. How do you create a thread?
	* By extending thread class.
	* By implementing Runnable interface.
16. Difference between yield and join?
	* Yield: if any threads execute yield method, thread scheduler checks if there are any threads have same or higher priority with current thread. If then, it will move current thread to Ready status and executes that thread. If not, current thread keeps executing.
	* Join: if current thread calls join on another thread, this thread will be running immediately. Current thread will be blocked until this thread completes executing.
17. What is deadlock?
	* A situation that two or more thread are blocked forever, waiting for each other.
18. How to avoid deadlock?
	* Apply for all resources at once
	* When a thread that occupies some resources and applies for other resources, if fails to apply, it release the resources it occupied.
	* Apply resources in a certain order and release following reversed order.
