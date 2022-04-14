# What are arrays?  What are some of the methods on arrays?

# What is JSON?
JSON stands for JavaScript Object Notation

JSON is a text format for storing and transporting data

JSON is "self-describing" and easy to understand

# When is a component re-rendered?

When it changes its state.

# What kind of CSS selectors do you know?

- class selector: .class
- ID selector: #id
- element: p 
- 


# What are the primitive data types in Javascript?  What makes them primitive?
string, number, bigint, boolean, undefined, symbol, and null

primitive types are only store values, they are on the stack, in running time. While Reference types are usally stores object, and there is only a Pointer to the memory where its stored in the stack. Reference types are stored on the HEAP



# What does the `&&` `||` `!` and `!!` operators do?

 - &&: check if both conditions are true
 - ||: check if A condition or B condition is true
 - ! : change condition to the opposite
 - !! : dont know

# What is Event Propagation and how can you prevent it?

    The stopPropagation() method of the Event interface prevents further propagation of the current event in the capturing and bubbling phases. It does not, however, prevent any default behaviors from occurring; for instance, clicks on links are still processed. If you want to stop those behaviors, see the preventDefault() method. 



# What does `event.preventDefault()` do?

The preventDefault() method cancels the event if it is cancelable, meaning that the default action that belongs to the event will not occur.

For example, this can be useful when:

- Clicking on a "Submit" button, prevent it from submitting a form
- Clicking on a link, prevent the link from following the URL

# What is `event.target` and `event.currentTarget`?
- target:  is the root element that raised the event.
- currentTarget: is the element handling the event.



# What is variable scope?
In simple terms, scope of a variable is its lifetime in the program. This means that the scope of a variable is the block of code in the entire program where the variable is declared, used, and can be modified.


# What are the falsy values in JavaScript?
- false
- 0
- -0
- undefined
- null
- NaN
- empty string values: '', "", ``
- On


# How to check if a value is falsy?
for example with ternary operators:

    0 ? 'truey' : 'falsey'

# What does "use strict" do?


# What's the value of `this` in JavaScript?
- in an object method: this refers to the object itself
- in global scope: it refers to the global oject (object.Window)
- in event handlers: it refers to the html element that recived the event

# What are Higher Order Functions?

# Why are functions called First-class Objects in Javascript?
A programming language is said to have First-class functions when functions in that language are treated like any other variable. For example, in such a language, a function can be passed as an argument to other functions, can be returned by another function and can be assigned as a value to a variable.

# What are Classes?

# What is Object Destructuring?


# What are the data types supported by JavaScript? What are the primitive/ reference data types?

# What does the `new` keyword do?

# What is a prompt box?

# What is asynchronous programming?

# What is a Promise?

# List some different ways an HTML element can be accessed in a JavaScript code.

# What are the variable naming conventions in JavaScript?
- Variable names cannot contain spaces.
- Variable names must begin with a letter, an underscore (_) or a dollar sign ($).
- Variable names can only contain letters, numbers, underscores, or dollar signs.
- Variable names are case-sensitive.

# What are Exports & Imports?

# Explain Implicit Type Coercion.

# What is recursion?

# What is the rest parameter and spread operator?

# What is JavaScript?

# What is a named Function?

# How to create an Object in JavaScript?

# What is the use of a constructor function?


# What are arrow functions?
    Arrow function is one of the features introduced in the ES6 version of JavaScript. It allows you to create functions in a cleaner way compared to regular functions. For example:

    ```js
    // function expression
    let x = function(x, y) {
        return x * y;
}
    ```

    ```js
    // using arrow functions
    let x = (x, y) => x * y;
}
    ```


# Which built in method is used for…
- returning character at the specified index: 
    - .charAt(index)
- combining two strings?
    - concat(str1, str2)

- calling a function for every element in an array?
    - array.forEach(function())

- returning the length of a string?
    - string.length 

- removing the last element from an array?
    - array.pop()

- adding new element to the end of the array?
    - array.push()

- reversing the order of the elements in array?
    - array.reverese()

- sorting elements?
    - array.sort()

- returning a substring?
    - string.substring(start, end)

- converting text to lower/upper case?
    - .toUpperCase()
    - .toLowerCase()

-   converting number to string datatype?
    - .toString()




# What is negative infinity?

# What kind of pop-up dialogs can you open from JavaScript?

# What does a ternary operator do?

condition ? doIfTrue : doIfFalse

# Can you tell us when would you utilize CSS float?




# Explain what are the difference between Get and Post?


# What Are The New Features Introduced In HTML5?

# Explain the difference between classes and IDs in CSS?
