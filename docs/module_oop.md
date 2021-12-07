# OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?

      In systems design, a fail-fast system is one which immediately reports at its interface any condition that is likely to indicate a failure. 
      Fail-fast systems are usually designed to stop normal operation rather than attempt to continue a possibly flawed process.
      Such designs often check the system's state at several points in an operation, so any failures can be detected early.
      The responsibility of a fail-fast module is detecting errors, then letting the next-highest level of the system handle them.

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?

      If we need to find the middle element in only one pass, the best method is to create two pointers.
      As we traverse the list starting from the first element, at each step one of the pointers is moved by one, while the other is moved by two. 
      At the moment, when the second pointer reaches the end of the list, the first pointer will be right on the middle element.
      
      https://www.geeksforgeeks.org/write-a-c-function-to-print-the-middle-of-the-linked-list/

#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?

         We sort the array and then we compare each element to the previous element.

               class Solution {
             public int findDuplicate(int[] nums) {
                 Arrays.sort(nums);
                 for (int i = 1; i < nums.length; i++) {
                     if (nums[i] == nums[i-1]) {
                         return nums[i];
                     }
                 }
                 return -1;
                }
            }

         Time complexity: O(n*lgn)
         Space complexity: O(1) (or O(n) if we are not allowed to modify the input array)
         
            Solution 2 – Using a set
            We store each element in a set as we iterate over the array, before saving a new element we simply check if it's already in the set.
                     class Solution {
                         public int findDuplicate(int[] nums) {
                             Set<Integer> seen = new HashSet<Integer>();
                             for (int num : nums) {
                                 if (seen.contains(num)) {
                                     return num;
                                 }
                             seen.add(num);
                             }
                             return -1;
                         }
                     }
                     Time complexity: O(n)
                     Space complexity: O(n)


#### What is a linked list? How to find if a linked list has a loop?

      A linked list is a linear data structure where each element is a separate object. 
      Each element (we will call it a node) of a list is comprising of two items - the data and a reference to the next node.
      The last node has a reference to null. The entry point into a linked list is called the head of the list. 
      It should be noted that head is not a separate node, but the reference to the first node. If the list is empty then the head is a null reference.
      
      https://www.geeksforgeeks.org/detect-loop-in-a-linked-list/

#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?

ArrayList:
- adding to the beginning (or near the beginning): the whole list needs to be "re-indexed": O(n)
- adding to the end (or near to the end): O(1)
- remove from the end: O(1)
- remove from elsewhere: "re-indexing": O(n)
- get (by index): O(1)
- contains: O(n)
LinkedList:
- adding to the beginning or end: O(1)
- adding elsewhere (somewhere middle): O(n)
- remove: O(n)
- get: O(n)
- contains: O(n)
HashMap:
- every task takes a single operation (except in edge cases, like hash clash).
Bubble Sort: -needs a nested for loop: O(n^2)
Quicksort:
- on average: O(log n)
- worst case: O(n^2)
Binary Search Tree:
- O(log n)
- worst case (degenerate tree): O(n)


#### How does HashMap work?

HashMap in Java works on hashing principle.
It is a data structure which allows us to store object and retrieve it in constant time O(1) provided we know the key.
In hashing, hash functions are used to link key and value in HashMap.
Objects are stored by calling put(key, value) method of HashMap and retrieved by calling get(key) method.
When we call put method, hashcode() method of the key object is called so that hash function of
the map can find a bucket location to store value object, which is actually an index of the internal array,
known as the table. HashMap internally stores mapping in the form of Map.Entry object which contains both key and value object.
When you want to retrieve the object, you call the get() method and again pass the key object.
This time again key object generate same hash code
(it's mandatory for it to do so to retrieve the object and that's why HashMap keys are immutable e.g. String)
and we end up at same bucket location.

https://medium.com/javarevisited/internal-working-of-hashmap-in-java-97aeac3c7beb#:~:text=HashMap%20uses%20multiple%20buckets%20and,bucket(singly%20linked%20list).

#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)

         Immutability allows you to get same hash code every time, for a key object. 
         So it actually solves most of the problems in one go. Also, this class must honor the hashCode() and equals() methods contract.

### Database

#### How can you connect your application to a database server? What are the possible ways?

       Example:

      private DataSource connect() throws SQLException {
      PGSimpleDataSource dataSource = new PGSimpleDataSource();
      dataSource.setDatabaseName("db_name");
      dataSource.setUser("username");
      dataSource.setPassword("password");
      System.out.println("Trying to connect...");
      dataSource.getConnection().close();
      System.out.println("Connection OK");
           return dataSource;
      }

      (You can outsource the datas to the enviromental variables)


      Set up the datasource
      Example:

          private void setup() throws SQLException {
           DataSource dataSource = connect();
           authorDao = new AuthorDaoJdbc(dataSource);
           bookDao = new BookDaoJdbc(dataSource, authorDao);
      }


     Run in a try catch the connect() method
     Example:
         public void run() { try {
         setup();
         } catch (SQLException throwables) {
         System.err.println("Could not connect to the database.");
         return;
         }
         mainMenu();
     }

#### What do you know about database normalization?

    Database Normalization is a technique of organizing the data in the database.
    Normalization is a systematic approach of decomposing tables to eliminate 
    data redundancy(repetition) and undesirable characteristics like Insertion,
    Update and Deletion Anomalies. 
    It is a multi-step process that puts data into tabular form, removing duplicated data from the relation tables.

Normalization is used for mainly two purposes:
- Eliminating redundant(useless) data.
- Ensuring data dependencies make sense i.e data is logically stored.

### Other

#### What is a garbage collector, in a nutshell?

      Garbage Collection tracks each and every object available in the JVM heap space and removes unused ones.

## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?

Upcasting: Upcasting is the typecasting of a child object to a parent object.
Upcasting can be done implicitly.
Upcasting gives us the flexibility to access the parent class members but it is not possible to access all the child class members using this feature.
Instead of all the members, we can access some specified members of the child class. For instance, we can access the overridden methods.

Downcasting: Similarly, downcasting means the typecasting of a parent object to a child object. Downcasting cannot be implicit.

https://www.geeksforgeeks.org/upcasting-vs-downcasting-in-java/


#### Which order should we catch the exceptions? Why?

      The order is whatever matches first, gets executed. If the first catch matches the exception, it executes, 
      if it doesn't, the next one is tried and on and on until one is matched or none are. 
      If the exceptions have parent-child relationship, the catch blocks must be sorted by the most specific exceptions first, 
      then by the most general ones.
      So, when catching exceptions you want to always catch the most specific first and then the most generic (as RuntimeException or Exception).



### Object-oriented

#### What is a class?
A class is a group of objects which have common properties.
It is a template or blueprint from which objects are created.
It is a logical entity. It can't be physical.

    A class in Java can contain:

          Fields
          Methods
          Constructors
          Blocks
          Nested class and interface


#### What is an object?
An entity that has state and behavior is known as an object e.g.,
chair, bike, marker, pen, table, car, etc. It can be physical or logical (tangible and intangible).
The example of an intangible object is the banking system.

      An object has three characteristics:
         State: represents the data (value) of an object.
         Behavior: represents the behavior (functionality) of an object such as deposit, withdraw, etc.
         Identity: An object identity is typically implemented via a unique ID. 
         The value of the ID is not visible to the external user. However, it is used internally by the JVM to identify each object uniquely.

For Example, Pen is an object. Its name is Reynolds; color is white, known as its state.
It is used to write, so writing is its behavior.
An object is an instance of a class. A class is a template or blueprint from which objects are created.
So, an object is the instance(result) of a class.

link: javatpoint.com/object-and-class-in-java

#### What is a constructor?

A Java constructor is special method that is called when an object is instantiated.
In other words, when you use the new keyword.
The purpose of a Java constructor is to initializes the newly created object before it is used.

#### Do we require parameter for constructors?

Not neccessarily. If we require parameters to the constructor it is called parametrized constructor.
But if we don't require any parameters it is called default constructor when there
is not required any outer parameteres to initantialize the class.

#### What is an interface?

Like a class, an interface can have methods and variables,
but the methods declared in an interface are by default abstract (only method signature, no body).  
Interfaces specify what a class must do and not how. It is the blueprint of the class.
An Interface is about capabilities like a Player may be an interface and any class implementing Player must be able to
(or must implement) move(). So it specifies a set of methods that the class has to implement.
If a class implements an interface and does not provide method bodies for all functions specified in the interface,
then the class must be declared abstract.


#### What are access modifiers?

The access modifiers in Java specifies the accessibility or scope of a field, method, constructor, or class.
We can change the access level of fields, constructors, methods, and class by applying the access modifier on it.
There are four types of Java access modifiers:
-Private: The access level of a private modifier is only within the class. It cannot be accessed from outside the class.
-Default: The access level of a default modifier is only within the package.
It cannot be accessed from outside the package. If you do not specify any access level, it will be the default.
-Protected: The access level of a protected modifier is within the package and outside the package through child class.
If you do not make the child class, it cannot be accessed from outside the package.
-Public: The access level of a public modifier is everywhere.
It can be accessed from within the class, outside the class, within the package and outside the package.

#### What is data hiding?

Data hiding is a technique of hiding internal object details, i.e., data members.
It is an object-oriented programming technique.
Data hiding ensures, or we can say guarantees to restrict the data access to class members.
It maintains data integrity.

Data hiding means hiding the internal data within the class to prevent its direct access from outside the class.

#### Can a static method use non-static members?

A static method can access only static members and can not access non-static members

#### What is the difference between hiding a static method and overriding an instance method?

-Overriding: The ability of a subclass to override a method allows a class to inherit from
a superclass whose behavior is close enough and then to modify behavior as needed.
The overriding method has the same name, number and type of parameters,
and return type as the method it overrides. Basically it’s the definition of method hiding in Java.

-Hiding: If a subclass defines a class method with the same signature as a class method in the superclass,
the method in the subclass hides the one in the superclass

-Differencies: The distinction between hiding and overriding has important implications.
The version of the overridden method that gets invoked is the one in the subclass.
The version of the hidden method that gets invoked depends on whether it is invoked from the superclass or the subclass.


#### Define the following terms: Instantiation, Attribute, Method

In Java, instantiation mean to call the constructor of a class that creates an instance or object of the type of that class.

#### Could we access a static variable (or method) from a non-static method? Why?

    Yes, a non-static method can access a static variable or call a static method in Java. 
    There is no problem with that because of static members i.e.
    both static variable and static methods belong to a class and can be called from anywhere, depending upon their access modifier.


#### Could we access a non-static variable (or method) from a static method? Why?

No, the only way to access a non-static variable from a static method is by creating an object of the class the variable belongs to.

#### How many instances you have of a static variable of a given class?

      A static variable is common to all the instances (or objects) of the class because it is a class level variable. 
      In other words you can say that only a single copy of static variable is created and shared among all the instances of the class.
      Memory allocation for such variables only happens once when the class is loaded in the memory.
      Like variables we can have static block, static method and static class, to read about them refer: static keyword in java.

#### Why is it not a good practice to write a lot of static methods?

The first point of OO design is the idea of messaging.
It means that a typical program following object-oriented principles consists of a network of self-contained objects
which are communicating with each other by sending messages
(instead of accessing each other data directly, it is also called incapsulation).
In the case of most popular OO languages messaging is implemented as invocations of object methods with parameters.

The second important point is dynamic dispatch also called polymorphism.
The idea of polymorphism is selecting of which implementation of the class should be used on the runtime.

#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?

      Static members/methods are used as in helper classes say like Math or in constants classes.
      Which helps other objects to utilize Strings or useful functions for which you do not need to create object but invoked using Class name,
      you can access them from everywhere.

#### What is the ‘this’ reference?

      The this is a keyword in Java which is used as a reference to the object of the current class,
      with in an instance method or a constructor.
      Using this you can refer the members of a class such as constructors, variables and methods.

#### What are base class, subclass and superclass?

In Java, as in other object-oriented programming languages, classes can be derived from other classes.
The derived class (the class that is derived from another class) is called a subclass.
The class from which its derived is called the superclass.

Subclass: is a class that derives from another class.
A subclass inherits state and behavior from all of its ancestors.
The term superclass refers to a class's direct ancestor as well as all of its ascendant classes.

Superclass : In object-oriented programming, a class from which other classes inherit code is called a superclass.
Furthermore, the class that inherits the code is called a subclass of that superclass.
Typically, a subclass inherits the instance variables and member functions of its superclass.

https://www.whitman.edu/mathematics/java_tutorial/java/javaOO/subclasses.html

#### Draw an object oriented family (as entities, with relations) on the whiteboard.

UML

#### Difference between overloading and overriding?


Overloading is about same function have different signatures.
Overriding is about same function, same signature but different classes connected through inheritance.
Overloading is an example of compiler time polymorphism and overriding is an example of run time polymorphism.



#### What are the Object Oriented Principles? Explain the concepts with realistic examples!

1.Encapsulation
2.Inheritance
3.Abstraction
4.Polymorphism


Encapsulation in OOP Meaning: In object-oriented computer programming languages,
the notion of encapsulation (or OOP Encapsulation) refers to the bundling of data,
along with the methods that operate on that data, into a single unit.
Many programming languages use encapsulation frequently in the form of classes.
A class is a program-code-template that allows developers to create an object that has both variables (data) and behaviors
(functions or methods).
A class is an example of encapsulation in computer science in that
it consists of data and methods that have been bundled into a single unit.

      public class Cat{
         private String name;
         
         public String getName(){
            return name;
         }
         
         public void setName(String name){
            this.name = name;
         }
      }

Inheritance is a mechanism that allows one class to gain the properties of another class,
in the same way, that a child inherits some attributes from each of their parents.
Inheritance allows programmers to create a new class that reuses the data members and methods of an existing class.

Abstraction occurs when a programmer hides any irrelevant data about an object or an instantiated
class to reduce complexity and help users interact with a program more efficiently.
The term abstraction vs encapsulation can be used to describe the process of hiding some of the information contained in an object or class,
but it may also refer to the object itself.
An abstraction is any named entity that contains a selection of data and behaviors specific to a particular usage of the originating entity.

Polymorphism means one name many forms.
It is further of two types — static and dynamic.
Static polymorphism is achieved using method overloading and dynamic polymorphism using method overriding.
It is closely related to inheritance. We can write a code that works on the superclass, and it will work with any subclass type as well.


#### What is method overloading?

         Method overloading:
         Method Overloading is a Compile time polymorphism.
         In method overloading, more than one method shares the same method name with different signature in the class.
         In method overloading, return type can or can not be be same, 
         but we must have to change the parameter because in java, 
         we can not achieve the method overloading by changing only the return type of the method.

#### What is method overriding?

         Method overrriding:
         Method Overriding is a Run time polymorphism. In method overriding, 
         derived class provides the specific implementation of the method that is already provided by the base class or parent class.
         In method overriding, return type must be same or co-variant (return type may vary in same direction as the derived class).

#### Explain how object oriented languages attempt to simplify memory management for Programmers.

      Java has automatic memory management,
      a nice and quiet garbage collector that works in the background to clean up the unused objects and free up some memory.

#### Explain the “Single Responsibility” principle!

      Single Responsibility principle is a basic concept of programming, which means every class has only one task to do. 
      That makes the code cleaner, more readable and easier to test or debug. 
      Every module or class should have responsibility over a single part of the functionality provided by the software,
      and that responsibility should be entirely encapsulated by the class.
      A class or module should have one, and only one, reason to be changed. 
      This principle states that if we have 2 reasons to change for a class,
      we have to split the functionality in two classes.
      Each class will handle only one responsibility and if in the future we need to make one change 
      we are going to make it in the class which handles it.
      When we need to make a change in a class having more responsibilities the change might affect the 
      other functionality related to the other responsibility of the class.
      
      https://medium.com/backticks-tildes/the-s-o-l-i-d-principles-in-pictures-b34ce2f1e898


#### What is an object oriented program? Explain, show.

      Object Oriented programming (OOP) is a programming paradigm that relies on the concept of classes and objects.
      It is used to structure a software program into simple, 
      reusable pieces of code blueprints (usually called classes),
      which are used to create individual instances of objects. 
      There are many object-oriented programming languages including JavaScript, C++, Java, and Python.
      
      A class is an abstract blueprint used to create more specific, concrete objects.
      Classes often represent broad categories, like Car or Dog that share attributes. 
      These classes define what attributes an instance of this type will have, 
      like color, but not the value of those attributes for a specific object.
      
      For example, say we created a class, Car, to contain all the properties a car must have, color, brand, and model.
      We then create an instance of a Car type object, myCar to represent my specific car.
      We could then set the value of the properties defined in the class to describe my car,
      without affecting other objects or the class template.
      We can then reuse this class to represent any number of cars.
      
      https://www.educative.io/blog/object-oriented-programming



#### How do you make a class immutable? What do you need to watch out for?

      Declare the class as final so it can’t be extended.
      Make all fields private so that direct access is not allowed.
      Don’t provide setter methods for variables
      Make all mutable fields final so that it’s value can be assigned only once.
      Initialize all the fields via a constructor performing deep copy.
      Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.


#### How many instances can be created for an abstract class?

      You cannot create an instance of an abstract class because it does not have a complete implementation. 
      The purpose of an abstract class is to function as a base for subclasses.
      It acts like a template, or an empty or partially empty structure, you should extend it and build on it before you can use it.



## Programming languages

### Java

#### What is autoboxing and unboxing?

      Autoboxing: Converting a primitive value into an object of the corresponding wrapper class is called autoboxing.
      For example, converting int to Integer class. 
      The Java compiler applies autoboxing when a primitive value is:
         -Passed as a parameter to a method that expects an object of the corresponding wrapper class.
         -Assigned to a variable of the corresponding wrapper class.
      
      Unboxing: Converting an object of a wrapper type to its corresponding primitive value is called unboxing. 
      For example conversion of Integer to int. The Java compiler applies unboxing when an object of a wrapper class is:
         -Passed as a parameter to a method that expects a value of the corresponding primitive type.
         -Assigned to a variable of the corresponding primitive type.

#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?

      short (-32768 to 32767)

#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?

The golden rule is that static code cannot access non-static members by their simple names.
The lifetime of a variable is the time during which the variable stays in memory and is therefore accessible during program execution.
The variables that are local to a method are created the moment the method is activated (exactly as formal parameters)
and are destroyed when the activation of the method terminates.

#### What is the purpose of the ‘equals()’ method?

The equals method in Java is invoked every time an object is compared with another object to see if they are equivalent
to each other or not i.e. are they the same object in terms of data type and value.

https://www.educative.io/edpresso/how-to-use-the-equals-method-in-java

#### What is the difference between '==' and 'equals()'?

In general, both equals() and “==” operator in Java are used to compare objects
to check equality but here are some of the differences between the two:
-The main difference between the .equals() method and == operator is that one is a method and the other is the operator.
-We can use == operators for reference comparison (address comparison) and .equals() method for content comparison.
In simple words, == checks if both objects point to the same memory location whereas .equals() evaluates to the comparison of values in the objects.

https://www.geeksforgeeks.org/difference-equals-method-java/

#### What does the ‘static’ keyword mean?

      The static keyword in Java is used for memory management mainly.
      We can apply static keyword with variables, methods, blocks and nested classes. 
      The static keyword belongs to the class than an instance of the class.
      
      The static can be:

            -Variable (also known as a class variable)
            -Method (also known as a class method)
            -Block
            -Nested class
       
       https://www.javatpoint.com/static-keyword-in-java


#### Why is the main() method declared as static? Explain.

In Java, to start a program is to call an existing public static void main(String[] args) method on a class.
- It must be public to be reachable from the outer world.
- It must be static to be callable before creating any objects.
- It is void since by design it does not return anything when the program ends normally.
- It is possible to pass (multiple) arguments after the name of the class to the java runtime –
these arguments are visible by the method through the args parameter.

#### What is the default access modifier in a class?

      Default – No keyword required: When no access modifier is specified for a class, method or data member 
      – It is said to be having the default access modifier by default. 
      Classes having default access modifier are accessible only within the same package. Default = package private.

#### What is the JVM?

      JVM (Java Virtual Machine) is an abstract machine. 
      It is a specification that provides runtime environment in which java bytecode can be executed.
      JVMs are available for many hardware and software platforms (i.e. JVM is platform dependent).
      
      A specification where working of Java Virtual Machine is specified. But implementation provider is independent to choose the algorithm. 
      Its implementation has been provided by Oracle and other companies.
      An implementation Its implementation is known as JRE (Java Runtime Environment).
      Runtime Instance Whenever you write java command on the command prompt to run the java class, an instance of JVM is created.
      
      https://www.javatpoint.com/jvm-java-virtual-machi

#### What is the difference between the JRE and the JDK?

      Java Development Kit (JDK) is a software development environment used for developing Java applications and applets.
      It includes the Java Runtime Environment (JRE), an interpreter/loader (Java), a compiler (javac), an archiver (jar), 
      a documentation generator (Javadoc), and other tools needed in Java development. 
      
      Now let us discuss JVM, which stands out for java virtual machine. It is as follows:
         -A specification where the working of Java Virtual Machine is specified. 
         But implementation provider is independent to choose the algorithm. Its implementation has been provided by Sun and other companies.
         -An implementation is a computer program that meets the requirements of the JVM specification.
         -Runtime Instance Whenever you write a java command on the command prompt to run the java class, an instance of JVM is created.


#### What is the difference between long and Long?

      Long is a wrapper class around the primitive long. 
      Therefore Long is an object; objects can be null, primitives can not. 
      After auto-boxing feature is released in java the primitive long can be automatically converted to Long, which is an object.

#### Can a long store bigger numbers than a Long?

      No, both can store numbers from -9223372036854775808 to 9223372036854775807.

#### What kind of packages do you know under java.util.* ? Bring at least 3 examples.

      - java.util.Arrays
      - java.util.Scanner
      - java.util.Collections
      - java.util.HashMap/HashSet/LinkedList
      - java.util.Formatter
      - java.util.Random
      - java.util.UUID

#### What are the access modifiers in Java? Which one could we use for class?

The access modifiers in Java specifies the accessibility or scope of a field, method, constructor, or class.
We can change the access level of fields, constructors, methods, and class by applying the access modifier on it.

There are four types of Java access modifiers:

      Private: The access level of a private modifier is only within the class. It cannot be accessed from outside the class.
      Default: The access level of a default modifier is only within the package. It cannot be accessed from outside the package. If you do not specify any access level, it will be the default.
      Protected: The access level of a protected modifier is within the package and outside the package through child class. If you do not make the child class, it cannot be accessed from outside the package.
      Public: The access level of a public modifier is everywhere. It can be accessed from within the class, outside the class, within the package and outside the package.

#### Can an “enum” contain methods in Java? Explain.

      Az enum  can have methods. You are not restricted to simple getter and setter methods.
      You can also create methods that make calculations based on the field values of the enum constant.
      If your fields are not declared final you can even modify the values of the fields (although that may not be so good an idea,
      considering that the enums are supposed to be constants).

#### When would you use a private/protected/public attribute? What is the difference?

      The difference is as follows:

      Public :: A public variable or method can be accessed directly by any user of the class.

      Protected :: A protected variable or method cannot be accessed by users of the class but can be accessed inside a subclass that inherits from the class.

      Private :: A private variable or method can only be accessed internally from the class in which it is defined.This means that a private variable or method cannot be called from a child that extends the class.

#### How do you prevent developers from subclassing a class?

You can prevent a class from being subclassed by using the final keyword in the class's declaration.

#### How do you prevent developers from overriding a method in a subclass?

Similarly, you can prevent a method from being overridden by subclasses by declaring it as a final method.

#### How do you prevent developers from changing the value of a variable?

Similarly, make the variable final.

#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!

I would use BigDecimal because BigDecimal could use well for high-precision arithmetic.
We also use it for calculations requiring control over scale and rounding off behavior.

A BigDecimal is an exact way of representing numbers.
A Double has a certain precision. Working with doubles of various magnitudes (say d1=1000.0 and d2=0.001)
could result in the 0.001 being dropped altogether when summing as the difference in magnitude is so large.
With BigDecimal this would not happen. The disadvantage of BigDecimal is that it's slower,
and it's a bit more difficult to program algorithms that way (due to + - * and / not being overloaded).

#### What happens if you try to call something, that you have no access to, because of data hiding?

The compiler throws an error: ". . . has private access in . . ."
It is illegal to access a variable declared private outside its class.

#### What happens if you try to delete/drop an item from an array, while you are iterating over it?

    ArrayList provides the remove() methods, like remove (int index) and remove (Object element),
    you cannot use them to remove items while iterating over ArrayList in Java because 
    they will throw ConcurrentModificationException if called during iteration.

#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?

In Java, if we remove items from a List while iterating it, it will throw java.util.ConcurrentModificationException.
Solution: (list.removeIf("A"::equals);)

#### What happens if you try to add an item to the end of an array, while you are iterating over it?

It is not possible, because arrays has a fixed size after they are created.
It you want to add an element to the end of an array, you have to create a new array with length n + 1 (if the original list’s length was n),
copy the original list elements to the new one, and add your element to the end of the new list.

#### If you need to access the iterator variable after a for loop, how would you do it?

I would save it into a variable which is declared out of the loop.

      int i;
      for (i = 0; i < numbers.size(); i++) {
          sum += numbers.get(i);
      }


#### Which interfaces extend the Collection interface in Java. Which classes?

Interfaces:
- List
- Set
- SortedSet
- NavigableSet
- Queue
- Deque

Classes:
- Class ArrayList
- Class LinkedList (also implements Deque )
- Class Vector. Class Stack

    https://www.javatpoint.com/collections-in-java

#### What is the connection between equals() and hashCode()? How are they used in HashMap?

hashCode method:
hashCode() method is used to get the hash Code of an object.
hashCode() method of object class returns the memory reference of object in integer form.
Definition of hashCode() method is public native hashCode().
It indicates the implementation of hashCode() is native because there is not any direct method in java to fetch the reference of object.
It is possible to provide your own implementation of hashCode().
In HashMap, hashCode() is used to calculate the bucket and therefore calculate the index.

equals() method:
equals method is used to check that 2 objects are equal or not.
This method is provided by Object class.
You can override this in your class to provide your own implementation.
HashMap uses equals() to compare the key whether the are equal or not.
If equals() method return true, they are equal otherwise not equal.


#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?

      There are two exception types, checked and unchecked (also called runtime). 
      The main difference is that checked exceptions are checked when compiled, while unchecked exceptions are checked at runtime.

      https://howtodoinjava.com/java/exception-handling/checked-vs-unchecked-exceptions-in-java/


#### What is Error in Java and how does it relate to Exception?

      Both errors and exceptions are subclasses of the throwable class. 
      Exceptions are related to the application itself while errors are related to the environment (JVM) in which the application is running.
      Errors cannot and should not be handled or caught. 
      They signal severe problems during runtime that should stop execution. 
      Two most common examples are stack overflow and out-of-memory errors.

#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?

      Java finally block is always executed whether an exception is handled or not. 
      Therefore, it contains all the necessary statements that need to be printed regardless of the exception occurs or not.
      The finally block follows the try-catch block.

#### What is the largest number you can work with in Java?

      The int type in Java can be used to represent any whole number from -2147483648 to 2147483647.

#### When you use method overriding, can you change the access level of the method, from protected to public? Why?When you use method overriding, can you change the access level of the method, from public to protected? Why?

      Yes, an overridden method can have a different access modifier but it cannot lower the access scope.
         Protected --> public :  Yes you can, because public is a higher scope than protected.
         Public --> protected : No you cant't, because protected is a lower scope than public.

#### Can the main method be overridden? Explain your answer!

     No, we cannot override main method of java because a static method cannot be overridden.

#### When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?

      An overriding method can throw any unchecked exceptions, regardless of whether the overridden method throws exceptions or not.
      However, the overriding method should not throw checked exceptions that are new or broader than the ones declared by the overridden method.
      The overriding method can throw narrower or fewer exceptions than the overridden method.

#### When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?

      The overriding method must NOT throw checked exceptions that are new or broader than those declared by the overridden method.

#### What does "final" mean in case of a variable, method or a class?

    - A final variable’s value cannot be modified or if it is a reference to an object, you cannot refer to another object with it.
    - A final method cannot be overridden.
    - A final class cannot be extended.

#### What is the super keyword?

      The super keyword in Java is a reference variable which is used to refer immediate parent class object.
      
      https://www.javatpoint.com/super-keyword

#### What are “generics”? When to use? Show examples.

Using java generics programmers are able to write more general methods.
It means that it is not necessary to specify the input type of a method,
therefore it can handle Strings, Integers, Doubles and so on.
It is very useful when for example we want to implement a sorting method.
If we use generics our method will handle more type of Lists.
Generics also provide compile-time type safety that allows programmers to catch invalid types at compile time.

      public class GenericMethodTest {
          // generic method printArray
          public static < E > void printArray ( E[] inputArray ) {
              // Display array elements
              for (E element : inputArray) {
                  System.out.printf("%s ", element);
              }
              System.out.println();
          }
      }


#### What is the benefit of having “generic” containers?

The possibility, of using the methods, the Class properties on different type of variables.
Make it String, Integer. primitive types, such as int are not usable in generic containers.

      public class Container<T> {
          private final T value;

          public Container(T value) {
              this.value = value;
          }

          public T getValue() {
              return value;
          }
      }
#### Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?
#### What is an annotation? What can be annotated and how? Show examples.

      Java Annotations allow us to add metadata information into our source code, 
      although they are not a part of the program itself.
      Annotations can be applied to the classes, interfaces, methods and fields.
      
        Examples: 
         - @Override
         - @TestAnnotation()
         - @Repeatable



### C&#35;

#### Explain the purpose of IL and how does it relate to CLR?
#### What does “managed code” mean?
#### What is an assembly?
#### What is the difference between an EXE and a DLL?
#### What is the difference between `dotnet build` and `dotnet restore`?
#### What is strong-typing versus weak-typing? Which is preferred? Why?
#### What is a namespace?
#### Explain sealed class in C#?
#### What is explicit vs. implicit conversion? Give examples of both of them.
#### Is a struct stored on the heap or stack?
#### Can a struct have methods?
#### Can DateTimes be null?
#### List out the differences between Array and ArrayList in C#?
#### How is the using() pattern useful? What is IDisposable? How does it support deterministic finalization?
#### How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?
#### Why to use keyword “const” in C#? Give an example.
#### What is the difference between “const” and “readonly” variables in C#?
#### What is a property in C#?
#### List out two different types of errors in C#?
#### What is the difference between “out” and “ref” parameters in C#?
#### Can we override private virtual method in C#?
#### What's the difference between IEquatable and just overriding Object.Equals()?
#### Explain the differences between public, protected, private and internal. Explain access modifier – “protected internal” in C#!
#### What’s the difference between using `override` and `new` keywords when defining method in child class?
#### Explain StringBuilder class in C#!
#### How we can sort the array elements in descending order in C#?
#### Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable).
#### What are Nullable Types in C#?
#### Conceptually, what is the difference between early-binding and late-binding?
#### What is delegate, event, callback, multicast delegate?
#### What is enum in C#?
#### What is null-conditional operator?
#### What is null-coalescing operator?
#### What is serialization?
#### What is the difference between Finalize() and Dispose() methods?
#### How do you inherit a class from another class in C#?
#### What is difference between “is” and “as” operators in C#?
#### What are indexers in C# .NET?
#### What is the difference between returning IQueryable<T> vs. IEnumerable<T>?
#### What is LINQ? Explain the idea of extension methods.
#### What are the advantages and disadvantages of lazy loading?
#### How to use of “yield” keyword? Mention at least one practical scenario where it can be used?
#### What are attributes in C#? Give some examples of usage of them.
#### By what mechanism does NUnit know what methods to test?
#### What is the GAC? What problem does it solve?
#### What is the largest number you can work with in C#?
