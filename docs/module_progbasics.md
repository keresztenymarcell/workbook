


Data structures
What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!
List is a container which can hold a fix number of items and these items should not be of the same type. Most of the data structures make use of list to implement their algorithms. Python has a set of built-in methods that you can use on lists/arrays.
append(): Adds an element at the end of the list
clear(): Removes all the elements from the list
copy(): Returns a copy of the list
count()	: Returns the number of elements with the specified value
extend(): Add the elements of a list (or any iterable), to the end of the current list
index(): Returns the index of the first element with the specified value
insert(): Adds an element at the specified position
pop(): Removes the element at the specified position
remove(): Removes the first item with the specified value
reverse(): Reverses the order of the list
sort(): Sorts the liston has a set of built-in methods that you can use on lists/arrays.




What is the difference between a list/array and a set?
Indexing - a list can be indexed by integer (starting from 0); a set cannot be indexed (there is no concept of the first item in a set except when it is iterated).
Slicing - a list can be sliced (using [a:b] notation); a Python set cannot be sliced.
Contents - a list can contain any mixture of data items; a set can only contain those data items which are hashable (i.e. the hash() function returns a value).
Duplicates - a list can contain duplicate data items - there is no limit on how many times items of equal value appear in the list; a set cannot contain duplicates.
Ordering - lists are ordered which means they retain ordering as determined by the program using the list; sets are not ordered - there is no concept of first, second etc - and there is no way that a programmer can control the order in which a set is iterated, displayed or otherwise presented. (Note ordering is not the same as being sorted - but sets can’t be sorted either).
membership - a membership test (the ‘in’ operator) on a list is a linear search from first to last ; a membership test on a set is based first on the hash() of the value being searched for. Searching a set is considerably more efficient when compared to a similar sized list.
Other capabilities - lists don’t have behaviours for creating new lists based on overlaps or differences between lists; sets on the other hand have a myriad of operations (and methods) for identifying the differences and overlaps between sets



What is the purpose and methods of a dictionary/map data structure?
In Python is an unordered collection of data values, used to store data values like a map, which unlike other Data Types that hold only single value as an element, Dictionary holds key:value pair. Key value is provided in the dictionary to make it more optimize.
clear(): Removes all the elements from the dictionary
copy(): Returns a copy of the dictionary
fromkeys(): Returns a dictionary with the specified keys and value
get(): Returns the value of the specified key
items(): Returns a list containing a tuple for each key value pair
keys(): Returns a list containing the dictionary's keys
pop(): Removes the element with the specified key
popitem(): Removes the last inserted key-value pair
setdefault(): Returns the value of the specified key. If the key does not exist: insert the key, with the specified value
update(): Updates the dictionary with the specified key-value pairs
values(): Returns a list of all the values in the dictionary

Python’s map() is a built-in function that allows you to process and transform all the items in an iterable without using an explicit for loop, a technique commonly known as mapping. map() is useful when you need to apply a transformation function to each item in an iterable and transform them into a new iterable. map() is one of the tools that support a functional programming style in Python.
map() loops over the items of an input iterable (or iterables) and returns an iterator that results from applying a transformation function to every item in the original input iterable.

>>> def square(number):
...    return number ** 2
...

>>> numbers = [1, 2, 3, 4, 5]

>>> squared = map(square, numbers)

>>> list(squared)
[1, 4, 9, 16, 25]

>>> str_nums = ["4", "8", "6", "5", "3", "2", "8", "9", "2", "5"]

>>> int_nums = map(int, str_nums)
>>> int_nums
<map object at 0x7fb2c7e34c70>

>>> list(int_nums)
[4, 8, 6, 5, 3, 2, 8, 9, 2, 5]

>>> str_nums
["4", "8", "6", "5", "3", "2", "8", "9", "2", "5"]



>>> string_it = ["processing", "strings", "with", "map"]
>>> list(map(str.capitalize, string_it))
['Processing', 'Strings', 'With', 'Map']

>>> list(map(str.upper, string_it))
['PROCESSING', 'STRINGS', 'WITH', 'MAP']

>>> list(map(str.lower, string_it))
['processing', 'strings', 'with', 'map']




Algorithms
Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
We can make a function call itself. This is known as recursion. A common example is a function which calculates numbers in the Fibonacci sequence: the zeroth number is 0, the first number is 1, and each subsequent number is the sum of the previous two numbers:

Rekurzió: A fibonacci szekvencia egy rekurzív függvény, bármikor amikor rekurziós függvényt hívunk, hogy ha van benne egy olyan feltétel, ami megállítja a rekurziós folyamatot

def fibonacci(n):
    if n == 0:
        return 0

    if n == 1:
        return 1

    return fibonacci(n - 1) + fibonacci(n - 2)


How do you find a max value in a list/array if you can’t use any built-in functions?
  maximum = list[0]
  for x in list:
    if x > maximum:
      maximum = x
  return maximum

How do you find the average of values in a list/array if you can’t use any built-in functions?
  total = 0
  length = 0
  for i in list:
    total += i 
    length += 1
  result = total / length
  return result
What do we call an *in-place* sort?
If we want to sort or reverse a list, we can either call a method on the list to modify it in-place, or use a function to return a modified copy of the list while leaving the original list untouched.
Explain an algorithm which sorts a list!

fruits = ['alma', 'körte', 'banán']
 
for fruit in fruits:
   print(fruits.sort())
print(fruits)

['alma', 'banán', 'körte']

fruits = ['alma', 'körte', 'banán']
 
for fruit in fruits:
   print(sorted(fruits))
print(fruits)

['alma', 'körte', 'banán']

Programming paradigms - procedural
What is the call stack?
Python stores information about functions which have been called in a call stack. Whenever a function is called, a new stack frame is added to the stack – all of the function’s parameters are added to it, and as the body of the function is executed, local variables will be created there. When the function finishes executing, its stack frame is discarded, and the flow of control returns to wherever you were before you called the function, at the previous level of the stack.

What is “Stack overflow”?
if we keep placing instances of the function on the stack we will eventually fill it up and cause a stack overflow. Python protects itself from stack overflows by setting a limit on the number of times that a function is allowed to recurse.

What are the main parts of a function?
Keyword def that marks the start of the function header.
A function name to uniquely identify the function.
Parameters (arguments) through which we pass values to a function. They are optional.
A colon (:) to mark the end of the function header.
Optional documentation string (docstring) to describe what the function does.
One or more valid python statements that make up the function body. Statements must have the same indentation level (usually 4 spaces).
An optional return statement to return a value from the function.

Programming languages - Python  
How do you use a dictionary in Python?
Python provides another composite data type called a dictionary, which is similar to a list in that it is a collection of objects. Lists elements are accessed by numerical index based on order, and dictionary elements are accessed by key.

Dictionaries and lists share the following characteristics:
Both are mutable.
Both are dynamic. They can grow and shrink as needed.
Both can be nested. A list can contain another list. A dictionary can contain another dictionary. A dictionary can also contain a list, and vice versa.

What does it mean that an object is immutable in Python?
These are of in-built types like int, float, bool, string, unicode, tuple. In simple words, an immutable object can’t be changed after it is created.To summarise the difference, mutable objects can change their state or contents and immutable objects can’t change their state or content.
Immutable: Boolean, Integer, Float, String, Tuple
Mutable: List, Dictionary, set

What is conditional expression in Python?
X if condition else Y

The condition is evaluated first. If condition is True, X is evaluated and its value is returned, and if condition is False, Y is evaluated and its value is returned.


What are different types of arguments in Python?
5 Types of Arguments in Python Function Definition:
Default arguments:
Default arguments are values that are provided while defining functions.
The assignment operator = is used to assign a default value to the argument.
Default arguments become optional during the function calls.
If we provide value to the default arguments during function calls, it overrides the default value.
The function can have any number of default arguments
Default arguments should follow non-default arguments.
 
def greet(name, msg="Good morning!"):
Keyword arguments:
Functions can also be called using keyword arguments of the form kwarg=value.
During function call, values passed through arguments need not be in the order of parameters in the function definition. This can be achieved by keyword arguments. But all the keyword arguments should match the parameters in the function definition

	def greet(kwarg = "Bruce"):
Positional arguments:
During function call, values passed through arguments should be in the order of parameters in the function definition. This is called positional arguments.
Keyword arguments should follow positional arguments only.

def demo(name,age):
   print(name + " is " + age + " years old")

demo("Mohan","20")

Arbitrary positional arguments:
Python allows us to have the arbitrary number of arguments. This is especially useful when we are not sure in the advance that how many arguments, the function would require. We define the arbitrary arguments while defining a function using the asterisk (*) sign.

def fruits(*fnames):
   for fruit in fnames:
       print(fruit)
fruits("Orange","Banana","Apple","Grapes")

Arbitrary keyword arguments.
If you do not know how many keyword arguments that will be passed into your function, add two asterisk: ** before the parameter name in the function definition.
This way the function will receive a dictionary of arguments, and can access the items accordingly:

def my_function(**kid):
  print("His last name is " + kid["lname"])

my_function(fname = "Tobias", lname = "Refsnes")

What is variable shadowing? (context: variable scope)
In computer programming, variable shadowing occurs when a variable declared within a certain scope (decision block, method, or inner class) has the same name as a variable declared in an outer scope. 
At the level of identifiers (names, rather than variables), this is known as name masking. This outer variable is said to be shadowed by the inner variable, while the inner identifier is said to mask the outer identifier. 
This can lead to confusion, as it may be unclear which variable subsequent uses of the shadowed variable name refer to, which depends on the name resolution rules of the language.

x = 0

def outer():
    x = 1

    def inner():
        x = 2
        print("inner:", x)

    inner()
    print("outer:", x)

outer()
print("global:", x)

# prints
# inner: 2
# outer: 1
# global: 0



What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
Every item in a list lives at its own unique index; which are in order, starting from 0.

If we remove an item, any item with an index greater than the one we've removed has now been shifted down.

                     foo = ['a', 'b', 'c', 'd'] 
                 for index in range(len(foo)): 
del foo[index]
Result is..
foo = ['a', 'd']


What is the "golden rule" of variable scoping in Python (context: LEGB)?
The concept of scope rules how variables and names are looked up in your code. 
It determines the visibility of a variable within the code. 
The scope of a name or variable depends on the place in your code where you create that variable. 
The Python scope concept is generally presented using a rule known as the LEGB rule.

The letters in the acronym LEGB stand for Local, Enclosing, Global, and Built-in scopes. This summarizes not only the Python scope levels but also the sequence of steps that Python follows when resolving names in a program.
Local (or function) scope is the code block or body of any Python function or lambda expression. This Python scope contains the names that you define inside the function. These names will only be visible from the code of the function. It’s created at function call, not at function definition, so you’ll have as many different local scopes as function calls. This is true even if you call the same function multiple times, or recursively. Each call will result in a new local scope being created.
A variable created inside a function is available inside that function:
def myfunc():
  x = 300
  print(x)
myfunc()
Enclosing (or nonlocal) scope is a special scope that only exists for nested functions. If the local scope is an inner or nested function, then the enclosing scope is the scope of the outer or enclosing function. This scope contains the names that you define in the enclosing function. The names in the enclosing scope are visible from the code of the inner and enclosing functions.
Global (or module) scope is the top-most scope in a Python program, script, or module. This Python scope contains all of the names that you define at the top level of a program or a module. Names in this Python scope are visible from everywhere in your code.
x = 300
def myfunc():
  print(x)
myfunc()
print(x)
Built-in scope is a special Python scope that’s created or loaded whenever you run a script or open an interactive session. This scope contains names such as keywords, functions, exceptions, and other attributes that are built into Python. Names in this Python scope are also available from everywhere in your code. It’s automatically loaded by Python when you run a program or script.

 What is the lifetime of variables?
The lifetime of a variable is the time during which the variable stays in memory and is therefore accessible during program execution.
The variables that are local to a method are created the moment the method is activated (exactly as formal parameters) and are destroyed when the activation of the method terminates.

If you need to access the iterator variable after a for loop, how would you do it in Python?
Print, use methods

What type of elements can a list contain in Python?
A list can contain any assortment of objects. The elements of a list can all be the same type:

a = [2, 4, 6, 8]
Or the elements can be of varying types: String, Integer, Float, Bool
a = [21.42, 'foobar', 3, 4, 'bark', False, 3.14159]
Lists can even contain complex objects, like functions, classes, and modules.

What is slice operator in Python and how to use?
The slice() function returns a slice object. list=[2,5,10,24,45] [1:4]
list = [:5:2]
 [start:end:step]
slice(start,end,step)
A slice object is used to specify how to slice a sequence. 
You can specify where to start the slicing, and where to end. 
You can also specify the step, which allows you to e.g. slice only every other item.

slice(start, end, step)
________________________________________________

a = ("a", "b", "c", "d", "e", "f", "g", "h")
x = slice(0, 8, 3)
print(a[x])

It will return every third item from the tuple.

What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
We are using For Loop to iterate each element in a given List. Inside the loop, we are performing arithmetic operations on elements of the first and second lists.

Addition: Adds one operand to the another.
Subtraction: Subtracts the second operand from the first.
Multiplication: Multiplies one operand by the other.
Division: Divides the first operand by the second.
Modulus: Divides the first INTEGER operand by the second, and returns the remainder.
Exponentiation: Lets you refer to a number in terms of a base value and an exponent.

NumList1 = [10, 20, 30]
NumList2 = [5, 2, 3]
add = []
sub = []
multi = []
div = []
mod = []
expo = []
 
for num in range(3):
    add.append( NumList1[num] + NumList2[num])        addition
    sub.append( NumList1[num] - NumList2[num])        subtraction
    multi.append( NumList1[num] * NumList2[num])      multiplication
    div.append( NumList1[num] / NumList2[num])        division
    mod.append( NumList1[num] % NumList2[num])        modulus
    expo.append( NumList1[num] ** NumList2[num])      exponentiation

What is the purpose of the in and not in membership operators in Python?

Membership operators are operators used to validate the membership of a value.
It tests for membership in a sequence, such as strings, lists, or tuples.

in operator : The ‘in’ operator is used to check if a value exists in a sequence or not. Evaluates to true if it finds a variable in the specified sequence and false otherwise.

Finding common member in list 
using 'in' operator
list1=[1,2,3,4,5]
list2=[6,7,8,9]
for item in list1:
    if item in list2:
        print("overlapping")      
else:
    print("not overlapping")
‘not in’ operator : Evaluates to true if it does not find a variable in the specified sequence and false otherwise.

x = 24
y = 20
list = [10, 20, 30, 40, 50 ];
  
if ( x not in list ):
   print("x is NOT present in given list")
else:
   print("x is  present in given list")
  
if ( y in list ):
   print("y is present in given list")
else:
   print("y is NOT present in given list")


What does the + operator mean when used with strings in Python?

We can also use the + operator to explicitly concatenate the strings.
String concatenation means add strings together.

x = "Codecool is "
y = "awesome"
z =  x + y
print(z)

For numbers, the + character works as a mathematical operator:

x = 5
y = 10
print(x + y)

If you try to combine a string and a number, Python will give you an error:

x = 5
y = "John"
print(x + y)

Explain f strings in Python?
We just append f at the start of the string and use {} to include our variable name, and we get the required results. An added functionality that f string provides is that we can put expressions in the {} brackets. This is quite useful as you can use any sort of expression inside these brackets. The expression can contain dictionaries or functions.

val = 'Geeks'
print(f"{val}for{val} is a portal for {val}.")
__________________________________________________________________
 
name = 'Tushar'
age = 23
print(f"Hello, My name is {name} and I'm {age} years old.")

Name 4 iterable types in Python! 
Strings:
my_string = “apple”
Tuples: Tuple items are ordered, unchangeable, and allow duplicate values.
my_tuple = ("apple", "banana", "cherry")
Lists: List items are ordered, changeable, and allow duplicate values.List items are indexed, the first item has index [0], the second item has index [1] etc.          my_list = ["apple", "banana", "cherry"]
Sets: Set items are unordered, unchangeable, and do not allow duplicate values.
my_set = {"apple", "banana", "cherry"}
What is the difference between list/set/dictionary comprehension and a generator expression in Python?
The generator yields one item at a time and generates item only when in demand.
Whereas, in a list comprehension, Python reserves memory for the whole list.
Thus we can say that the generator expressions are memory efficient than the list.


Does the order of the function definitions matter in Python? Why?
It doesn't matter in which order the functions are created, but it is a good thing if you make your functions in a logical order for later purposes. It only matters when the call to the function is done.

What does unpacking mean in Python?
We can use * to unpack the list so that all elements of it can be passed as different parameters.

# A sample function that takes 4 arguments
# and prints the,
def fun(a, b, c, d):
    print(a, b, c, d)
# Driver Code
my_list = [1, 2, 3, 4]
# Unpacking list into four arguments
fun(*my_list)
Output : (1, 2, 3, 4)
What happens when you try to assign the result of a function which has no return statement to a variable in Python?
You can omit the return value of a function and use a bare return without a return value. You can also omit the entire return statement. In both cases, the return value will be None.

Software engineering
 Debugging

What techniques can you use while debugging a program in Python?
Print and check: 
The simplest but powerful method is to print some particular variables and check if their values are as expected or not.
Assert and check:
Python gives us more flexibility when using assert. We can use the -0 parameter to close all the assert statements in the program when starting the Python interpreter. After that, all the assert methods will not work.
Although the Assert and Check method is a little more flexible than the Print and Check, lots of assert statements will also make our code a bit confusing and unreadable.
Using logging Module:
Python has an important module named logging. Replacing print or assert to logging methods is a more professional and powerful way to debug. Actually, it is a “heavy weapon” for a Python project. Because it gives us lots of flexibility and abilities to debug, record and monitor our programs.
Pdb:
Python debugger pdb, let the program run in a single step mode, and you can check the running status at any time. The pdb is Python's build-in debugger tool. There are some other debugger tools such as web-pdb, pudb and so on. In most cases, the pdb is useful enough.
Integrated Development Environment:
VSC - Visual Studio Code
PyCharm
Eclipse
etc..

Pen and Paper:
Sometimes your mind is not very clear, writing it down with paper and pen is a good way to straighten out your thinking.


What does step over, step into and step out mean while using the debugger?
Step over – An action to take in the debugger that will step over a given line. If the line contains a function the function will be executed and the result returned without debugging each line.
Step into – An action to take in the debugger. If the line does not contain a function it behaves the same as “step over” but if it does the debugger will enter the called function and continue line-by-line debugging there.
Step out – An action to take in the debugger that returns to the line where the current function was called.

How can you start to debug a program from a certain line using the debugger?
Set a breakpoint at a given line.

Version control

What are the advantages of using a version control system?
With a VCS, everybody on the team is able to work absolutely freely - on any file at any time. The VCS will later allow you to merge all the changes into a common version. There's no question where the latest version of a file or the whole project is. It's in a common, central place: your version control system. Other benefits of using a VCS are even independent of working in a team or on your own.

What is the difference between the working directory, the staging area and the repository in git?
1. working tree: The Working Tree is the area where you are currently working. It is where your files live. This area is also known as the “untracked” area of git. Any changes to files will be marked and seen in the Working Tree. 
2.staging area: The Staging Area is when git starts tracking and saving changes that occur in files. These saved changes reflect in the .git directory. That is about it when it comes to the Staging Area.
3. repository: The Local Repository is everything in your .git directory. Mainly what you will see in your Local Repository are all of your checkpoints or commits. It is the area that saves everything.

What are remote repositories in git?
A remote in Git is a common repository that all team members use to exchange their changes. In most cases, such a remote repository is stored on a code hosting service like GitHub or on an internal server.

Why does a merge conflict occur?
A merge conflict happens when two branches both modify the same region of a file and are subsequently merged. Git can't know which of the changes to keep, and thus needs human intervention to resolve the conflict.

Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
Add the files in your new local repository. This stages them for the first commit.
$ git add <file_name> or < . > (it will add every file)
Commit the files that you've staged in your local repository.
$ git commit -m "First commit message"
Push the files that you’ve committed in your local repository. 
$ git push

What does it mean atomic commits and descriptive commit messages?
“Atomic commit” is basically a fancy way of saying a commit that commits one and only one thing. It’s a single complete unit of work, and those messages are meaningful and on the point. pl. ‘Implement main function’


What’s the difference between git and GitHub?
Git is a version control system that lets you manage and keep track of your source code history. Github is a cloud-based hosting service that lets you manage Git repositories.

Software design
Clean code

What does clean code mean?
Clean code is a set of principles that seeks code to be: Readable. Maintainable. Extendable.
Clean code is a reader-focused development style that produces software that’s easy to write, read, and maintain. 
Clean code is code that is easy to understand and easy to change.

What steps do we usually do during a clean code refactoring?
Running the program results in the exact same behaviour before and after refactoring.

Error handling
What is exception handling?
An exception is an event, which occurs during the execution of a program that disrupts the normal flow of the program's instructions. In general, when a Python script encounters a situation that it cannot cope with, it raises an exception. 
An exception is a Python object that represents an error.

What are the basics of exception handling in Python?
An exception is an error that happens during execution of a program. When that
error occurs, Python generate an exception that can be handled, which avoids your
program to crash.
Try: It will run the code block in which you expect an error to occur.
Except: Here, you will define the type of exception you expect in the try block (built-in or custom).
Else: If there isn't any exception, then this block of code will be executed (consider this as a remedy or a fallback option if you expect a part of your script to produce an exception).
Finally: used in try...except blocks. It defines a block of code to run when the try...except...else block is final.
The finally block will be executed no matter if the try block raises an error or not.
This can be useful to close objects and clean up resources.

In which case should we catch an exception? Why?
You should catch the exception when you are in the method that knows what to do.
Why? Missing...

What can/should we do with an exception in the ‘except’ block?
The try and except block in Python is used to catch and handle exceptions.


What does the else and finally statement do in a try-except block in Python?
Else: If there isn't any exception, then this block of code will be executed (consider this as a remedy or a fallback option if you expect a part of your script to produce an exception).
Finally: used in try...except blocks. It defines a block of code to run when the try...except...else block is final.
The finally block will be executed no matter if the try block raises an error or not.
This can be useful to close objects and clean up resources.

Software Development Methodologies
What is the main goal of a retrospective meeting?
A retrospective is a meeting held after a product ships to discuss what happened during the product development and release process, with the goal of improving things in the future based on those learnings and conversations.

Programming environment
Unix

What is UNIX and what is Linux?
UNIX is an operating system which was first developed in the 1960s, and has been under constant development ever since. It is a stable, multi-user, multi-tasking system for servers, desktops and laptops.

UNIX systems also have a graphical user interface (GUI) similar to Microsoft Windows which provides an easy to use environment. However, knowledge of UNIX is required for operations which aren't covered by a graphical program, or for when there is no windows interface available, for example, in a telnet session.

There are many different versions of UNIX, although they share common similarities. The most popular varieties of UNIX are Sun Solaris, GNU/Linux, and MacOS X.

Linux is the clone of Unix. It has several features similar to Unix, but they still have some key differences. Before Linux and Windows, computer world was dominated by Unix. Unix is a copyrighted name and IBM AIX, HP-UX and Sun Solaris are only Unix operating system remained till date.


Comparison
Linux
Unix
Definition
It is an open-source operating system which is freely available to everyone.
It is an operating system which can be only used by its copyrighters.
Examples
It has different distros like Ubuntu, Redhat, Fedora, etc
IBM AIX, HP-UX and Sun Solaris.
Users
Nowadays, Linux is in great demand. Anyone can use Linux whether a home user, developer or a student.
It was developed mainly for servers, workstations and mainframes.
Usage
Linux is used everywhere from servers, PC, smartphones, tablets to mainframes and supercomputers.
It is used in servers, workstations and PCs.
Cost
Linux is freely distributed,downloaded, and distributed through magazines also. And priced distros of Linux are also cheaper than Windows.
Unix copyright vendors decide different costs for their respective Unix Operating systems.
Development
As it is open source, it is developed by sharing and collaboration of codes by world-wide developers.
Unix was developed by AT&T Labs, various commercial vendors and non-profit organizations.
Manufacturer
Linux kernel is developed by the community of developers from different parts of the world. Although the father of Linux, Linus Torvalds oversees things.
Unix has three distributions IBM AIX, HP-UX and Sun Solaris. Apple also uses Unix to make OSX operating system.
GUI
Linux is command based but some distros provide GUI based Linux. Gnome and KDE are mostly used GUI.
Initially it was command based OS, but later Common Desktop Environment was created. Most Unix distributions use Gnome.
Interface
The default interface is BASH (Bourne Again SHell). But some distros have developed their own interfaces.
It originally used Bourne shell. But is also compatible with other GUIs.
File system support
Linux supports more file system than Unix.
It also supports file system but lesser than Linux.
Coding
Linux is a Unix clone,behaves like Unix but doesn't contain its code.
Unix contain a completely different coding developed by AT&T Labs.
Operating system
Linux is just the kernel.
Unix is a complete package of Operating system.
Security
It provides higher security. Linux has about 60-100 viruses listed till date.
Unix is also highly secured. It has about 85-120 viruses listed till date
Error detection and solution
As Linux is open-source,whenever a user post any kind of threat, developers from all over the world start working on it. And hence, it provides faster solution.
In Unix, users have to wait for some time for the problem to be resolved.



What do we call the shell in Linux?
Simply put, the shell is a program that takes commands from the keyboard and gives them to the operating system to perform. On most Linux systems a program called bash (which stands for Bourne Again SHell, an enhanced version of the original Unix shell program, sh , written by Steve Bourne) acts as the shell program.

What does root mean in a Linux environment?
The root is the user name or account that by default has access to all commands and files on a Linux or other Unix-like operating system. It is also referred to as the root account, root user, and the superuser.

How do you access your personal files in Linux?
In Linux, personal data is stored in /home/username folder.
In the Windows world, each disk drive is labeled with an identifying letter such as C: for your hard disk and D: for the CD/DVD drive. In the Linux world, however, everything is part of the same filesystem organization. As such, if you have two or three hard disks, a CD drive, and a USB stick all plugged in, they will all be part of the same folder structure.



How can you install an application in Linux?
You can use the apt application to install from a repository, or you can use the dpkg app to install apps from . deb files.

To install from a software repository, there's usually a command:
$ sudo dnf install inkscape
The actual command you use depends on what distribution of Linux you use. Fedora uses dnf, OpenSUSE uses zypper, Debian and Ubuntu use apt, Slackware uses sbopkg, FreeBSD uses pkg_add, and Illumos-based OpenIndiana uses pkg.
eg. $ sudo apt install python-qt5 (for Ubuntu)

If you want to install deb packages in the command line, you can use either the apt command or the dpkg command. The apt command actually uses the dpkg command underneath it, but apt is more popular and easier to use.
If you want to use the apt command for deb files, use it like this:
sudo apt install path_to_deb_file
If you want to use the dpkg command for installing deb packages, here’s how to do it:
sudo dpkg -i path_to_deb_file
In both commands, you should replace path_to_deb_file with the path and name of the deb file you’ve downloaded.

What is package management in Linux, what are repositories?
In simpler words, a package manager is a tool that allows users to install, remove, upgrade, configure and manage software packages on an operating system. The package manager can be a graphical application like a software center or a command line tool like apt-get or pacman.
The repositories contain software packages of different kind. Repositories also have metadata files that contain information about the packages such as the name of the package, version number, description of package and the repository name etc. This is what you see if you use the apt show command in Ubuntu/Debian.


How do you navigate in the filesystem with the command line?
pwd - To find out where your directory is in relationship to the rest of the filesystem:
pwd
eg. You should get back some information that looks like this:
/usr/share 

ls - to look at the contents of a directory.
Use the ls command:
ls
List of items in the directory, eg.:
adduser            groff                          pam-configs
applications       grub                           perl
apport             grub-gfxpayload-lists          perl5
. . .
To list all of the contents in an extended form, we can use the -l flag (for “long” output):
ls -l
total 440
drwxr-xr-x   2 root root  4096 Apr 17  2014 adduser
drwxr-xr-x   2 root root  4096 Sep 24 19:11 applications
drwxr-xr-x   6 root root  4096 Oct  9 18:16 apport
. . .

To get a listing of all files, including hidden files and directories, you can add the -a flag. 
ls -a
.  ..  .bash_logout  .bashrc  .profile
(there are three hidden files in this demonstration, Often, configuration files are stored as hidden files, like here.
Dot and double dot entries are referring to related directories. single dot - current directory, double dot - this directory’s parent directory.)

cd - moving around the file system
eg. Going back to the /usr/share directory by typing this:
cd /usr/share		(changing a directory by giving an absolute path)
Relative paths refer to directories in relation to the current directory. Any directory within the current directory can be referenced by name without a leading slash. 
eg. change to the locale directory within /usr/share from our current location by typing:
cd locale
We can likewise move multiple directory levels with relative paths by providing the portion of the path that comes after the current directory’s path. From here, we can get to the LC_MESSAGES directory within the en directory by typing:
cd en/LC_MESSAGES
To move up one level, we can type:
cd ..		This takes us to the /usr/share/locale/en directory.
A shortcut that will always take you back to your home directory is to use cd without providing a directory:
cd

What do the following commands do: mkdir, rm, cat, cp, touch?
mkdir - use this command to create one or more new directories. This command can create multiple directories at once as well as set the permissions for the directories. It is important to note that the user executing this command must have enough permissions to create a directory in the parent directory, or he/she may recieve a ‘permission denied’ error.
mkdir [options...] [directories ...]

rm - used to remove objects such as files, directories, symbolic links and so on from the file system. rm removes references to objects from the filesystem, where those objects might have had multiple references (for example, a file with two different names). By default, it does not remove directories.
rm [OPTION]... FILE...

cat - reads data from the file and gives their content as output. It helps us to create, view, concatenate files.
$cat filename
$cat file1 file2
$cat -n filename	To view contents of a file preceding with line numbers
example:-cat-n  geeks.txt
1)This is geeks
2)A unique array


cp - to copy files or group of files or directory. It creates an exact image of a file on a disk with different file name. cp command require at least two filenames in its arguments.
cp [OPTION] Source Destination
cp [OPTION] Source Directory
cp [OPTION] Source-1 Source-2 Source-3 Source-n Directory

First and second syntax is used to copy Source file to Destination file or Directory.
Third syntax is used to copy multiple Sources(files) to Directory.
Two file names : If the command contains two file names, then it copy the contents of 1st file to the 2nd file. If the 2nd file doesn’t exist, then first it creates one and content is copied to it. But if it existed then it is simply overwritten without any warning.
cp Src_file Dest_file
Example:
$ ls
a.txt

$ cp a.txt b.txt

$ ls
a.txt  b.txt
One or more arguments : If the command has one or more arguments, specifying file names and following those arguments, an argument specifying directory name then this command copies each source file to the destination directory with the same name, created if not existed but if already existed then it will be overwritten
cp Src_file1 Src_file2 Src_file3 Dest_directory
Example:
$ ls
a.txt  b.txt  new

Initially new is empty
$ ls new

$ cp a.txt b.txt new

$ ls new
a.txt  b.txt

touch - to create, change and modify timestamps of a file. Basically, there are two different commands to create a file in the Linux system which is as follows:
cat command: It is used to create the file with content.
touch command: It is used to create a file without any content. The file created using touch command is empty. This command can be used when the user doesn’t have data to store at the time of file creation.
touch file_name

How can you look up what a command does in Linux if you have no internet connection?
If you’re not sure how to use a specific command, run the command with the -h or –help switches. You’ll see usage information and a list of options you can use with the command. For example, if you want to know how to use the wget command, type wget –help or wget -h.

What does the following commands do: head, tail, more, less?
HEAD - print the top N number of data of the given input. By default, it prints the first 10 lines of the specified files. If more than one file name is provided then data from each file is preceded by its file name.
head [OPTION]... [FILE]...
$ head state.txt
Andhra Pradesh
Arunachal Pradesh
Assam
Bihar
Chhattisgarh
Goa
Gujarat
Haryana
Himachal Pradesh
Jammu and Kashmir
-n num: Prints the first ‘num’ lines instead of first 10 lines. num is mandatory to be specified in command otherwise it displays an error.
$ head -n 5 state.txt
Andhra Pradesh
Arunachal Pradesh
Assam
Bihar
Chhattisgarh
-c num: Prints the first ‘num’ bytes from the file specified. Newline count as a single character, so if head prints out a newline, it will count it as a byte. num is mandatory to be specified in command otherwise displays an error.
-q: It is used if more than 1 file is given. Because of this command, data from each file is not precedes by its file name.
-v: By using this option, data from the specified file is always preceded by its file name.

TAIL - print the last N number of data of the given input. By default it prints the last 10 lines of the specified files. If more than one file name is provided then data from each file is precedes by its file name.
tail [OPTION]... [FILE]...
Its options are same as head’s options: (-n num, -c num, -q, -v)

MORE - to view the text files in the command prompt, displaying one screen at a time in case the file is large (For example log files). The more command also allows the user do scroll up and down through the page.
more [-options] [-num] [+/pattern] [+linenum] [file_name]
[-options]: any option that you want to use in order to change the way the file is displayed. Choose any one from the followings: (-d, -l, -f, -p, -c, -s, -u)
[-num]: type the number of lines that you want to display per screen.
[+/pattern]: replace the pattern with any string that you want to find in the text file.
[+linenum]: use the line number from where you want to start displaying the text content.
[file_name]: name of the file containing the text that you want to display on the screen.
While viewing the text file use these controls:
Enter key: to scroll down line by line.
Space bar: To go to the next page.
b key: To go back one page.

LESS - to read contents of text file one page(one screen) per time. It has faster access because if file is large, it don’t access complete file, but access it page by page.

For example, if it’s a large file and you are reading it using any text editor, then the complete file will be loaded to main memory, but less command don’t load entire file, but load it part by part, which makes it faster.

less filename
-E : causes less to automatically exit the first time it reaches end of file.
-f : forces non-regular file to open.
-F : causes less to exit if entire file can be displayed on first screen
-g : highlight the string which was found by last search command
-G : suppresses all highlighting of strings found by search commands
-i : cause searches to ignore case
-n : suppresses line numbers
-p pattern : it tells less to start at the first occurrence of pattern in the file
-s : causes consecutive blank lines to be squeezed into a single blank line

How do you download a file from the internet using the terminal?
Wget is the non-interactive network downloader which is used to download files from the server even when the user has not logged on to the system and it can work in the background without hindering the current process.
wget [option] [URL]
Example :
1. To simply download a webpage:
wget http://example.com/sample.php

2. To download the file in background
wget -b http://www.example.com/samplepage.php

-v / –version : to display the version of the wget available on your system.
-h / –help : to print a help message displaying all the possible options of the line command that is available with the wget command line options.
-o logfile : to direct all the messages generated by the system to the logfile specified by the option and when the process is completed all the messages thus generated are available in the log file.
-b / –background : to send a process to the background as soon as the process has started so that other processes can be carried out.
-a : to append the output messages to the current output log file without overwriting the file as in -o option the output log file is overwritten but by using this option the log of the previous command is saved and the current log is written after that of the previous ones.
-i : to read URLs from file. If -i is specified as file, URLs are read from the standard input. If this function is used, no URLs need be present on the command line. If there are URLs both on the command line and in an input file, those on the command lines will be the first ones to be retrieved. The file need not be an HTML document if the URLs are just listed sequentially.
-t number / –tries=number : to set number of retries to a specified number of times. Specify 0 or inf for infinite retrying. The default is to retry 20 times, with the exception of fatal errors like connection refused or link not found, which are not retried once the error has occurred.
-c : to resume a partially downloaded file if the resume capability of the file is yes otherwise the downloading of the file cannot be resumed if the resume capability of the given file is no or not specified.
-w : to set the system to wait the specified number of seconds between the retrievals. 
-r : to turn on the recursive retrieving of the link specified in case of fatal errors also. This option is a recursive call to the given link in the command line.

