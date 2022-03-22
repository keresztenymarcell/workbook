


Mellékletek terület
# Web with Python questions
## Software design
### Clean code

#### Point out 5 suggestions, how to format an SQL query!
Indentation/Alignment, Spaces, Variable Naming Conventions (Letter-casing, Descriptive Names), 
Write Useful Comments, Use the WITH Clause(WITH clause is basically a replacement for a normal subquery.)

#### What layers can you name in a simple web application?
Presentation layer (PL)
    PL displays the user interface and makes user interaction more straightforward. 
    The presentation layer has UI components that render and show data for users.
    There are also user process components that set the user interactions. 
    PL provides all the required information to the client side. The primary goal 
    of the Presentation layer is to get input data, process users’ requests, 
    send them to data service, and show the results.

Data service layer (DSL)
    DSL transmits data processed by the Business logic layer to the Presentation layer. 
    This layer guarantees data security, isolating the business logic from the client side.

Business logic layer (BLL)
    BLL is responsible for the proper data exchange.
    This layer defines the logic for business operations and rules. 
    Logging in the website is an example of a business logic layer.

Data access layer (DAL)
    DAL offers simplified access to data stored in persistent storages like 
    binary and XML files. Data access layer also manages CRUD operations — create, read, update, delete.

### Error handling
#### What error can occur, when an array does not have an element on the requested index?
IndexOutOfRangeException

#### What is the “finally” block, and how would you use it?
Finally: used in try...except blocks. It defines a block of code to run when the try...except...else block is final.
The finally block will be executed no matter if the try block raises an error or not.
This can be useful to close objects and clean up resources.

#### Why should we catch special exception types?
If an exception is thrown, this try catch block will handle the exception to
ensure that the application does not cause an unhandled exception, user error,
or crash the application. ... Catching specific types of exceptions can help tailor how to handle them.


### Security
#### What is SQL injection? How to protect an application against it?
SQL injection is a type of injection attack. Injection attacks occur when 
maliciously crafted inputs are submitted by an attacker, causing an application 
to perform an unintended action. Because of the ubiquity of SQL databases, SQL 
injection is one of the most common types of attack on the internet.

Protection:
    Always use parameterized statements where available, they are your number one protection against SQL injection.
    You need to be very careful to escape characters everywhere in your codebase where an SQL statement is constructed.

#### What is XSS? How to protect an application against it?
sriptel fertőzött weboldalról pl cookiekan tárolt adatot szerezhet meg a támadó, json filekkal

Cross-site scripting (also known as XSS) is a web security vulnerability 
that allows an attacker to compromise the interactions that users have with 
a vulnerable application.
An attacker who exploits a cross-site scripting vulnerability is typically able to:

    Impersonate or masquerade as the victim user.
    Carry out any action that the user is able to perform.
    Read any data that the user is able to access.
    Capture the user's login credentials.
    Perform virtual defacement of the web site.
    Inject trojan functionality into the web site.

There are three main types of XSS attacks. These are:

    Reflected XSS, where the malicious script comes from the current HTTP request.
    Stored XSS, where the malicious script comes from the website's database.
    DOM-based XSS, where the vulnerability exists in client-side code rather than server-side code.

Preventing:
    Filter input on arrival. At the point where user input is received, filter as 
    strictly as possible based on what is expected or valid input.
    
    Encode data on output. At the point where user-controllable data is output in HTTP responses,
    encode the output to prevent it from being interpreted as active content. 
    Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.
    
    Use appropriate response headers. To prevent XSS in HTTP responses that aren't intended 
    to contain any HTML or JavaScript, you can use the Content-Type and X-Content-Type-Options 
    headers to ensure that browsers interpret the responses in the way you intend.
    
    Content Security Policy. As a last line of defense, you can use 
    Content Security Policy (CSP) to reduce the severity of any XSS vulnerabilities that still occur.


#### How to properly store passwords?
Salted password hashing 
Hashelés:  Alkotunk egy olyan függvényt, ami egy egyedi bemenetre ad egy egyedi kimenetet úgy,
hogy az a kimenetből nem tudjuk visszafejteni a bemenetet. Az SHA-256 hash függvény eredménye egy 
olyan karaktersorozat, amiből az eredeti jelszót nem tudjuk visszafejteni. A jelszót ellenőrizni viszont könnyű.
Vagyis nincs is szükségünk az eredeti jelszóra, elég ha van egy ujjlenyomatunk (hashünk),
amivel össze tudjuk hasonlítani a megadott jelszó hash-ét.

salted: Minden felhasználóhoz kitalálunk egy egyedi kulcsot, amit elmentünk a felhasználóval, 
és ezt beleszerkesztjük a jelszóba hashelés előtt.


#### What is HTTPS?
(A HTTP egy kérés-válasz alapokon működő protokoll a kliens és a szerver között.
Ez a protokoll biztosítja az ügyfelek számára, hogy weboldalakat kérjenek a webkiszolgálóktól. 
Ebben az aspektusban az ügyfelek a webböngészők, a szerverek pedig a webhely adatokat tároló szerverek.
Amikor a felhasználó böngészni szeretne egy adott weboldalon, a számítógépén 
használt böngésző HTTP kérés üzenetet küld a weboldal szerverének. 
A szerver a kért weboldallal válaszol. Az ügyfelek és a webszerverek ezzel a kérés-válasz 
módszerrel kommunikálnak egymással.)

 a HTTP Secure. A HTTPS a HTTP kiterjesztése, nem pedig egy másik protokoll. 
 A HTTPS-t leggyakrabban a webszerverek és a böngészők közötti biztonságos kommunikáció
 megvalósítására alkalmazzák . A HTTP protokoll titkosított, SSL csatornán keresztül üzemeltetett változata.


#### What is encryption and decryption?
Encryption software converts large volumes of data into cryptic text or numbers using algorithms.
Only those people or systems with the decryption key can decipher the encrypted data.
Adatfolyam eltorzítása egy algoritmus és egy titkos kulcs felhasználásával olyan módon,
hogy annak eredeti tartalmára ne lehessen következetni. 
A titkosított folyamból az eredeti adatsor dekódolással nyerhető vissza.


#### What is hashing?
Alkotunk egy olyan függvényt, ami egy egyedi bemenetre ad egy egyedi kimenetet úgy,
hogy az a kimenetből nem tudjuk visszafejteni a bemenetet. Az SHA-256 hash függvény eredménye egy 
olyan karaktersorozat, amiből az eredeti jelszót nem tudjuk visszafejteni. A jelszót ellenőrizni viszont könnyű.
Vagyis nincs is szükségünk az eredeti jelszóra, elég ha van egy ujjlenyomatunk (hashünk),
amivel össze tudjuk hasonlítani a megadott jelszó hash-ét.

#### What is the difference between encryption and hashing? When would you use which?
a különbség a hasás és a titkosítás között az, hogy a hashing kimenet nem 
konvertálható vissza az eredeti üzenetre vagy az adatokra, 
míg a titkosított üzenet visszaállítható az eredeti üzenetre.

A hashing-t jelszavak, fájlok küldésére és keresésre használják.
A titkosítás érzékeny üzleti információk továbbítására használható.

#### What encryption methods do you know?
There are two fundamental types of encryption: symmetric encryption (which uses a single key)
and asymmetric encryption (which requires two keys).
Továbbá a titkosításban és a dekódolásban két módszer van. 
Ezeket szimmetrikus és aszimmetrikus titkosításnak nevezik. A szimmetrikus titkosítás ugyanazt 
a kulcsot használja a titkosításhoz és a dekódoláshoz. Az aszimmetrikus titkosítás két kulcsot 
(nyilvános és magánkulcsot) használ a titkosításhoz és a dekódoláshoz.
pl. AES, RSA


#### What hashing methods do you know?
MD5, SHA2, CRC32


#### How/where would you store sensitive data (like db password, API key, ...) of your application?
 The best would be to have a separate file with secrets encrypted.
 This file should be stored on some area which is not accessible by the application server (outside its scope).



## Computer science

### Algorithms - logikát írja le

#### What is the difference between Stack and Queue data structure?
Difference Between Stack and Queue
featuredStack and Queue both are the non-primitive data structures. 
The main differences between stack and queue are that stack uses LIFO 
(last in first out) method to access and add data elements whereas 
Queue uses FIFO (First in first out) method to access and add data elements.

Stack has only one end open for pushing and popping the data elements on
the other hand Queue has both ends open for enqueuing and dequeuing the data elements.

Stack and queue are the data structures used for storing data elements and
are actually based on some real world equivalent. For example, the stack is a
stack of CD’s where you can take out and put in CD through the top of the stack 
of CDs. Similarly, The queue is a queue for Theatre tickets where the person 
standing in the first place, i.e., front of the queue will be served first and 
the new person arriving will appear in the back of the queue (rear end of the queue).


#### What is BubbleSort? Describe the main logic of this sorting algorithm.
A buborék rendezése egy egyszerű algoritmus, amely összehasonlítja a tömb első elemét a következővel. 
Ha a tömb aktuális eleme számszerűen nagyobb, mint a következő, akkor az elemeket felcseréljük. 
Hasonlóképpen, az algoritmus bejárja a tömb teljes elemét.


#### Explain the process of finding the maximum and minimum value in a list of numbers!
Ciklus, elmentjük a nagyobb elemet a változóba a ciklus végén - > max / min.
#### Explain the process of calculating the average value in an array of numbers!
sum/length


#### What is Big O complexity? Explain time and space complexity!
Algoritmusok hatékonyságának a mérőszáma. 
Time
By definition, time complexity is the amount of time taken by an algorithm to run, as a function
of the length of the input. Here, the length of input indicates the number of operations to be
performed by the algorithm. This gives a clear indication of what exactly Time complexity tells us.

Space
The space complexity of an algorithm or a computer program is the amount of memory space required
to solve an instance of the computational problem as a function of characteristics of the input. 
It is the memory required by an algorithm until it executes completely.


#### Explain the process of calculating the average value in a list of numbers!
sum/length

### Procedural
#### How the CASE condition works in SQL?
The CASE statement goes through conditions and returns a value when the first condition is met 
(like an if-then-else statement). So, once a condition is true, it will stop reading and return 
the result. If no conditions are true, it returns the value in the ELSE clause.

If there is no ELSE part and no conditions are true, it returns NULL.


#### How the switch-case condition works in JavaScript?
The JavaScript switch keyword is used to create multiple conditional statements,
allowing you to execute different code blocks based on different conditions.

The switch has one or more case blocks and an optional default.


const expr = 'Papayas';
switch (expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Mangoes':
  case 'Papayas':
    console.log('Mangoes and papayas are $2.79 a pound.');
    // expected output: "Mangoes and papayas are $2.79 a pound."
    break;
  default:
    console.log(`Sorry, we are out of ${expr}.`);
}
> "Mangoes and papayas are $2.79 a pound."
> 
> 
#### How to achieve a switch-case-like structure in Python?
def switch_demo(argument):
    switcher = {
        1: "January",
        2: "February",
        3: "March",
        4: "April",
        5: "May",
        6: "June",
        7: "July",
        8: "August",
        9: "September",
        10: "October",
        11: "November",
        12: "December"
    }
    print switcher.get(argument, "Invalid month")
In the above example, when you pass an argument to the switch_demo function, it is 
looked up against the switcher dictionary mapping. If a match is found, the associated 
value is printed, else a default string (‘Invalid Month’) is printed. The default string 
helps implement the ‘default case’ of a switch statement.


#### Explain variable scoping in Python?
LEGB


#### What’s the difference between const and var in JavaScript?
a VAR deklaráció hatóköre (scope-ja) globális. Amennyiben függvényen belül használjuk, akkor lokális.
Ez azt jelenti, ha függvényen kívül deklarálunk var kulcsszóval, akkor a teljes kódra érvényes változót kapunk.
A scriptet az értelmező úgy futtatja, hogy a globális hatókörben talált deklarációt fölemeli a script tetejére.  - HOISTING
VAR újradeklarálható.

Let- NEM deklarálható újra
let developer = "George";
let developer = "Peter"; 
hibára fut!



let message = "Everything is alright.";
let eventCounter = 0;
if (eventCounter < 1) {
    let message = "Nothing is wrong.";    console.log(message);
}
console.log(message);

-
Nothing is wrong.
Everything is alright.

A blokkon belül LET-tel deklarált változó a blokk futásának idejére elfedi a globális változót.
A blokk vége után visszaáll a blokk előtti helyzet.


CONST
A CONST kulcsszó szintén deklarációra használható. A vele létrehozott változó értéke nem változtatható,
így helyesebb ha konstansnak nevezzük. Érvényességét tekintve a LET-re hasonlít legjobban,
hiszen „block scope” érvényességű a létrehozott konstans. Amiben mégis különböző a LET-tel létrehozott változótól, 
hogy ebben az esetben a változó értéke sem írható fölül.


#### How the list comprehension looks like in Python?
PL. [expression for item in list]


#### How the “ternary expression” looks like in Python?
a if a < b else b


#### How the ternary expression looks like in JavaScript?
condition ? exprIfTrue : exprIfFalse


#### How to import a function from another module in Python?
In [1]:
from myfunctions import plustwo

plustwo(3)

Out[1]:
5


#### How to import a function from another module in JavaScript?
export function Course() {
    this.id = '';
    this.name = '';
};
models/student.js

import { Course } from './course.js';

export function Student() {
    this.firstName = '';
    this.lastName = '';
    this.course = new Course();
};


### Functional
#### What is recursion?
Recursion
We can make a function call itself. This is known as recursion. 
A common example is a function which calculates numbers in the Fibonacci sequence: the zeroth number is 0,
the first number is 1, and each subsequent number is the sum of the previous two numbers:

def fibonacci(n):
    if n == 0:
        return 0

    if n == 1:
        return 1

    return fibonacci(n - 1) + fibonacci(n - 2)
Whenever we write a recursive function, we need to include some kind of condition which will allow it to stop recursing
– an end case in which the function doesn’t call itself. 
In this example, that happens at the beginning of the sequence: the first two numbers are 
not calculated from any previous numbers – they are constants.


#### Write a recursive function which calculates the Fibonacci numbers!
const number = parseInt(prompt('Enter the number of terms: '));
let n1 = 0, n2 = 1, nextTerm;

console.log('Fibonacci Series:');

for (let i = 1; i <= number; i++) {
    console.log(n1);
    nextTerm = n1 + n2;
    n1 = n2;
    n2 = nextTerm;
}


#### How to store a function in a variable in Python?
def myfunction():
    value = "myvalue"
    return value

var = myfunction()
print(var)

>>> "myvalue"


#### List the ways of defining a callable logical unit in JavaScript!
list, call


#### What is an event listener? How to attach one?
element.addEventListener(event, function, useCapture);

The addEventListener() method attaches an event handler to the specified element.

The addEventListener() method attaches an event handler to an element without overwriting existing event handlers.
The first parameter is the type of the event (like "click" or "mousedown" or any other HTML DOM Event.)
The second parameter is the function we want to call when the event occurs.
The third parameter is a boolean value specifying whether to use event bubbling or event capturing. This parameter is optional.


#### How to trigger an event in JavaScript?
For example, to trigger a click event on any element, you use the click() method:

el.click();
Code language: CSS (css)
The input text and text area elements provide the focus() and blur() methods for triggering the focus and blur events:

el.focus();
el.blur();
Code language: CSS (css)
The form element has the submit() and reset() methods for triggering the submit and reset events:

const frm = document.querySelector('form');
// trigger the submit event
frm.submit();

// trigger the reset event
frm.reset();
Code language: JavaScript (javascript)
To trigger other events such as the mousedown or change, you use the following triggerEvent() helper function:

function triggerEvent(el, type) {
    // IE9+ and other modern browsers
    if ('createEvent' in document) {
        var e = document.createEvent('HTMLEvents');
        e.initEvent(type, false, true);
        el.dispatchEvent(e);
    } else {
        // IE8
        var e = document.createEventObject();
        e.eventType = type;
        el.fireEvent('on' + e.eventType, e);
    }
}
Code language: JavaScript (javascript)
Suppose that you have an input text:

<input type="text" name="username">
Code language: HTML, XML (xml)
The following binds an event handler to the click event:

const input = document.querySelector('input[type="text"]');
input.addEventListener('change', (e) => {
    console.log('Input changed');
});
Code language: JavaScript (javascript)
To trigger the change event, you use the triggerEvent() function as follows:

triggerEvent(input, 'change');


#### What is a callback function? Tell some examples of its usage.
In computer programming, a callback function, is any executable code that is passed as an argument
to other code that is expected to call back (execute) the argument at a given time.

This execution may be immediate as in a synchronous callback, or it might happen at a
later time as in an asynchronous callback.

A JavaScript Callback is a function passed as an argument to another function.

In the above example, we passed in as an argument the numbers 100 and the 200.

If we instead passed in a function, that function we pass in would be called a callback.

function addTwoNumberFunctions(functionOne, functionTwo) {
    var functionAdditionResult = functionOne() + functionTwo();
    return functionAdditionResult;
}

function functionOneHundred() { return 100; }

function functionTwoHundred() { return 200; }

addTwoNumberFunctions(functionOneHundred, functionTwoHundred);
In this example, the two functions we are passing in (functionOneHundred and functionTwoHundred) are both Callback Functions in JavaScript.

(setTimeout pl ilyen fv.)


#### What is a Python decorator? How does it work? Tell some examples of its usage.
They “decorate” or “wrap” another function and let you execute 
code before and after the wrapped function runs.

Decorators allow you to define reusable building blocks that can change 
or extend the behavior of other functions. And they let you do that without 
permanently modifying the wrapped function itself. The function’s behavior changes only when it’s decorated.

Now what does the implementation of a simple decorator look like? In basic terms
, a decorator is a callable that takes a callable as input and returns another callable.

The following function has that property and could be 
considered the simplest decorator one could possibly write:

def null_decorator(func):
    return func
As you can see, null_decorator is a callable (it’s a function), it takes another callable 
as its input, and it returns the same input callable without modifying it.

Let’s use it to decorate (or wrap) another function:

def greet():
    return 'Hello!'

greet = null_decorator(greet)

>>> greet()
'Hello!'

Putting an @null_decorator line in front of the function definition is
the same as defining the function first and then running through the 
decorator. Using the @ syntax is just syntactic sugar, and a shortcut for this commonly used pattern.


#### What is the difference between synchronous and asynchronous execution?
Synchronous execution means the first task in a program must finish processing
before moving on to executing the next task whereas asynchronous execution means
a second task can begin executing in parallel, without waiting for an earlier task to finish.
https://www.koyeb.com/blog/introduction-to-synchronous-and-asynchronous-processing


Technical Examples
We have selected 4 common examples of when synchronous and asynchronous processing are used in applications.

Synchronous Processing
User Interfaces: User interface (UI) designs are typically synchronous. 
Since UIs are spaces where humans and computers interact, it is ideal for 
them to replicate the communication standards and practices humans are familiar
with. Humans expect an immediate response when they interact with a computer!
HTTP APIs: HTTP APIs pass requests and responses in a synchronous fashion.
Client programs sending HTTP requests usually expect a fast answer from the web server.

Asynchronous Processing
Batch-processing: is a data-processing method to handle large amounts of data 
asynchronously. With asynchronous batch-processing, large batches of data are 
processed at scheduled times to avoid blocking computing resources.

Long-running tasks: such as fulfilling an order placed on an e-commerce site are
best handled asynchronously. There is no need to block resources while this task is executed.


## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?
Connect to PostgreSQL database server using psql
Connect to PostgreSQL database server using pgAdmin
create account, db, row stb, IDE


#### When do you use the DISTINCT keyword in SQL?
The SELECT DISTINCT statement is used to return only distinct (different) values.


#### Talk about the behavior/goal of these base SQL clauses: WHERE, GROUP BY, HAVING, ORDER BY?
The WHERE clause filters records by extracting only those records that fulfill a specified condition. 

Contrast this to the GROUP BY clause, which is used to group like column values into a single row.

This is useful as it allows you to summarize information.  For instance you can use aggregate
functions such as SUM and AVERAGE to calculate values.

In this example
SELECT   SalesOrderID,
         SUM(OrderQty* UnitPrice) As TotalPrice
FROM     Sales.SalesOrderDetail
GROUP BY SalesOrderID


The HAVING clause comes after GROUP BY. GROUP BY is usually paired with aggregate
functions such as COUNT, MAX, MIN — and in this case — SUM. 

The ORDER BY statement is used to sort values. 
(The ORDER BY clause’s purpose is to sort the query result by specific columns.
The GROUP BY clause’s purpose is summarize unique combinations of columns values.)


#### What are aggregate functions in SQL? Give 3 examples.
AVG – calculates the average of a set of values.
COUNT – counts rows in a specified table or view.
MIN – gets the minimum value in a set of values.
MAX – gets the maximum value in a set of values.
SUM – calculates the sum of values.


#### What kind of JOIN types do you know in SQL? Could you give examples?
There are mainly four types of joins that you need to understand. They are:

INNER JOIN
FULL JOIN
LEFT JOIN
RIGHT JOIN
You can refer to the below image.
https://www.edureka.co/blog/sql-joins-types


#### What are the constraints in sql?
SQL constraints are a set of rules implemented on tables in relational
databases to dictate what data can be inserted, updated or deleted in its tables. 
NOT NULL Constraint
UNIQUE Constraint
DEFAULT Constraint
CHECK Constraint
PRIMARY KEY Constraint
FOREIGN KEY Constraint


#### What is a cursor in SQL? Why would you use one?
To execute SQL statements, a work area is used by the Oracle engine
for its internal processing and storing the information. This work area
is private to SQL’s operations. The ‘Cursor’ is the PL/SQL construct that
allows the user to name the work area and access the stored information in it.


#### What are database indexes? When to use?
Indexes are a powerful tool used in the background of a
database to speed up querying. Indexes power queries by 
providing a method to quickly lookup the requested data.


#### What are database transactions? When to use?
A transaction, in the context of a database, is a logical unit
that is independently executed for data retrieval or updates. 
Experts talk about a database transaction as a “unit of work”
that is achieved within a database design environment.


#### What kind of database relations do you know? How to define them?
https://condor.depaul.edu/gandrus/240IT/accesspages/relationships.htm
One-To-One Relationship
A one-to-one (1:1) relationship means that each record in Table A relates to one, 
and only one, record in Table B, and each record in Table B relates to one, and 
only one, record in Table A. Look at the following example of tables from 
a company's Employees database:

One-To-Many Relationship
A one-to-many (1:N) relationship means a record in Table A can relate to zero
, one, or many records in Table B. Many records in Table B can relate to one 
record in Table A. The potential relationship is what's important; for a single
record in Table A, there might be no related records in Table B, or there might 
be only one related record, but there could be many. Look at the following 
tables about a company's Customers and Orders.

Many-To-Many Relationship
Examine the sample data below. These tables hold data about employees and
the projects to which they are assigned. Each project can involve more than 
one employee and each employee can be working on more than one project 
(the "do more with less" thing). This constitutes a many-to-many (N:N) relationship.

#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” 
### (postcode, city, street name and address). How would you query all records related to Miskolc?
WHERE address LIKE '%Miskolc%'


#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?
Create or select a folder where the SVN repository is going to be stored
Use TortoiseSVN to create a repository
Select your candidate database in SSMS Object Explorer
Link SQL Source Control to the repository folder


### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?
HTML is the HyperText Markup Language, which is designed to create 
structured documents and provide for semantic meaning behind the documents.
HTML5 is the next version of the HTML specification.

XML is the Extensible Markup Language, which provides rules for creating,
structuring, and encoding documents. You often see XML being used to store 
data and to allow for communication between applications. It's programming
language-agnostic - all of the major programming languages provide mechanisms 
for reading and writing XML documents, either as part of the core or in external libraries.

XHTML is an XML-based HTML. It serves the same function as HTML, but with 
the same rules as XML documents. These rules deal with the structure of the markup.


#### How to include a JavaScript file in a webpage?
In HTML, JavaScript code is inserted between <script> and </script> tags.


#### How to include a CSS file in a webpage?
<head>
<link rel="stylesheet" href="mystyle.css">
</head>


#### How to select an element using its id in CSS?
write a hash (#) character, followed by the id of the element.


#### How to select elements using their class in CSS?
write a hash (.) character, followed by the class of the element.


#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?
.alpha .beta


#### How to select all list items in all ordered lists on the page in CSS?
ol > li


#### How to select elements using their attributes in CSS?
<a href="http://www.disney.com" target="_blank">disney.com</a>

a[target="_blank"] {
  background-color: yellow;
}


#### What are UX and UI?
UX
A UX design az angol “User Experience design” rövidítése, magyarul a 
felhasználói élményt értjük alatta. Minden olyan érzelem és élmény,
amelyet a felhasználó a termék vagy szolgáltatás használata közben
átél, a felhasználói élmény részét képezi. 


UI
A legegyszerűbben megfogalmazva, a UI design feladata, hogy a tartalmat 
és a már meglévő szerkezetet a lehető legvonzóbb módon tálalja a látogatók
számára. Következésképp a UI designhoz sok terület tartozik – beleértve több 
UX területet is. Ilyen például a vizuális design (pl. vizuális stílus útmutató 
vagy pixelpontos elemek) vagy a navigációs elemek (pl. keresőmező, csúszka,
lapozás, ikonok, címkék) megtervezése, kialakítása


MI A KÜLÖNBSÉG A UX ÉS UI KÖZÖTT?
Nézzük a UI/UX közti különbséget egy autógyártási hasonlat segítségével. 

Mi itt a UX designer célja? Az, hogy a vezetési élmény a lehető legjobb 
legyen. Azon dolgozik, hogy az ülés ergonomikus legyen, a kormányt, a 
sebváltót és a pedálokat könnyű legyen kezelni. A visszajelző lámpák pedig 
csak a fontos dolgokat mutassák és csak a megfelelő pillanatban. 

Ezzel szemben a UI azért felel, hogy a kormány ne szögletes legyen és a 
pedálok jól illeszkedjenek a lábformához. Hogy a visszajelző lámpák ikonjai 
beszédesek és szabványosak legyenek. Sőt, a UI designer figyel az üléshuzatra
is. A kényelmen túl ugyanis az egységes megjelenést, az adott iparág sajátosságait,
a hangnemet, illetve az üzleti szempontokat is figyelembe veszi.


#### Please list some points that an application should fulfill to have good UX.
Design Should Concentrate on User Experience. ...
Websites Are Scanned, Not Read. ...
Users Want Clarity and Simplicity. ...
Common Design Elements Versus Creativity. ...
Know the Audience. ...
Visual Hierarchy. ...
User Experience Qualities


#### What is XML, XSLT, DTD?
Az XML-formátumban szereplő információ publikálásakor szükség van arra, 
hogy a jelölőelemeket a megfelelő szövegstílusokkal helyettesítsük. 
Az XSL, az XSLT szabvánnyal kiegészülve arra készült, hogy megfeleljen 
ezen követelményeknek. Egy XML elem tartalma alapvetően nem rendelkezik
stílussal. A megjelenítéshez stíluslapokat használhatunk.

Ugyanazt a stíluslapot több dokumentumnál is felhasználhatjuk. A DTD 
a stíluslapszerkesztő számára olyan, mint egy követendő specifikáció.
Egy XML dokumentumhoz több stíluslapot is rendelhetünk. Az XSL szabvány 
nem más, mint olyan formázó objektumok halmaza, mint a blokk- és soros elemek,
vagy a táblázatcellák. Ezek mindegyike számos jellemzővel rendelkezik annak érdekében,
hogy a dokumentum tartalmát professzionális módon lehessen formázni, megjeleníteni.
Az XSL egy absztrakt szabvány. Az objektumtípusoknak elemeknek felelnek meg, 
a tulajdonságoknak pedig azok jellemzői. A szabvány definiál e célra egy DTD-t 
ez a Formatting Objects DTD vagy FO DTD. Ebben a DTD-ben olyan elemek szerepelnek,
mint például a „block”, vagy olyan jellemzők, mint a „text-align”. Ennek a DTD-nek 
megfelelő dokumentumokban ezekkel az elemekkel kell körülvenni a formázásra szánt objektumokat.

Az XSL feldolgozónak érteni kell az FO DTD-nek megfelelő dokumentumokat. 
Az XSLT szabály azt a mechanizmust írja le, amellyel a forrás XML 
dokumentumot publikálásra alkalmas formára hozhatjuk. Az XSLT képes:

·        elő és utótagokkal kiegészíteni a tartalmat

·        elemeket törölni, létrehozni, átsorolni, és sorba rendezni

·        újrafelhasználni az elemeket az objektum egy másik részén

·        az adatokat egyik XML formáról egy másikra, vagy HTML formára alakítani

Az XSLT feldolgozó kész XML dokumentumból állít elő egy másik XML dokumentumot.
A kimeneti dokumentum sokszor egy másik DTD-nek felel meg, mint a bemeneti 
dokumentum. Ezt az átalakítást az XSLT szabványnak megfelelő stíluslappal végzi
az XSLT feldolgozó. Az átalakítás a stíluslapban megadott mintaillesztő szabályoknak (template) megfelelően történik.

Az FO elemeket tartalmazó XSL állományok mellett a másik legnépszerűbb kimeneti formátum a HTML..


#### What is the difference between HTML and XML?
The key difference between HTML and XML is that HTML displays data and
describes the structure of a webpage, whereas XML stores and transfers data.
XML is a standard language which can define other computer languages, 
but HTML is a predefined language with its own implications.


### Javascript

#### What is javascript?
JavaScript is a scripting language that enables you to create dynamically 
updating content, control multimedia, animate images, and pretty much
everything else. (Okay, not everything, but it is amazing what you can
achieve with a few lines of JavaScript code.)


#### When to use AJAX? Bring examples of its usage.
AJAX stands for Asynchronous JavaScript and XML. It is used for allowing 
the client side of an application to communitcate with the server side of the application. 

Auto-Complete - google
Voting and Rating - reddit
Updating With User Content - twitter
Form Submission & Validation
Chat Rooms And Instant Messaging
External Widgets
Lightboxes instead of pop-ups


#### What is DOM and how to manipulate it from Javascript?
The Document Object Model (DOM) represents that same document so i
t can be manipulated. The DOM is an object-oriented representation 
of the web page, which can be modified with a scripting language such as JavaScript.

getelementsby..., queryselector...,appendchild...removechild stb.


#### What are events and how/why to use them in Javascript?
What are Events in JavaScript?
Javascript has events that provide a dynamic interface to a webpage. 
These events are connected to elements in the Document Object Model(DOM).

Also, these events by default use the bubbling propagation i.e, upwards in
the DOM from children to parent. We can bind events either as inline or in 
an external script. With the help of JavaScript, you can detect when certain 
events happen, and cause things to occur in response to those events.

Types of Events in JavaScript
There are different types of events in JavaScript that are used to react to events.
Here, we will discuss some of the famous or most commonly used events such as:

Onclick
Onkeyup
Onmouseover
Onload
Onfocus


#### What is event bubbling/capturing? How would you use it?
When an event happens on an element, it first runs the handlers on it,
then on its parent, then all the way up on other ancestors.


There’s another phase of event processing called “capturing”. 
It is rarely used in real code, but sometimes can be useful.

The standard DOM Events describes 3 phases of event propagation:

Capturing phase – the event goes down to the element.
Target phase – the event reached the target element.
Bubbling phase – the event bubbles up from the element.


#### What is JSON and how do we use it?
JavaScript Object Notation (JSON) is a standard text-based format for representing 
structured data based on JavaScript object syntax. It is commonly used for 
transmitting data in web applications (e.g., sending some data from the server 
to the client, so it can be displayed on a web page, or vice versa). 
You'll come across it quite often, so in this article we give you all you need 
to work with JSON using JavaScript, including parsing JSON so you can access 
data within it, and creating JSON.


JavaScript Object Notation (JSON) is a way of storing information 
in an organized and easy manner. The data must be in the 
form of a text when exchanging between a browser and a server

{
   "book": [
	
      {
         "id":"01",
         "language": "Java",
         "edition": "third",
         "author": "Herbert Schildt"
      },
	
      {
         "id":"07",
         "language": "C++",
         "edition": "second",
         "author": "E.Balagurusamy"
      }
   ]
}

<html>
   <head>
      <title>JSON example</title>
      <script language = "javascript" >
         var object1 = { "language" : "Java", "author"  : "herbert schildt" };
         document.write("<h1>JSON with JavaScript example</h1>");
         document.write("<br>");
         document.write("<h3>Language = " + object1.language+"</h3>");  
         document.write("<h3>Author = " + object1.author+"</h3>");   

         var object2 = { "language" : "C++", "author"  : "E-Balagurusamy" };
         document.write("<br>");
         document.write("<h3>Language = " + object2.language+"</h3>");  
         document.write("<h3>Author = " + object2.author+"</h3>");   
  
         document.write("<hr />");
         document.write(object2.language + " programming language can be studied " + "from book written by " + object2.author);
         document.write("<hr />");
      </script>
   </head>
   
   <body>
   </body>
</html>


## Software engineering

### Version control

#### What type of branching strategy would you use?
Branching Strategy #1: GitHub Flow
Branching Strategy #2: GitFlow
Branching Strategy #3: The Forking Workflow
https://www.cloudbees.com/blog/branching-strategy


#### What would you do if you find a bug on the production code (master branch)?
Create a "Hotfix" Branch from master. Fix your Problem and merge 
them back in both branches. Don't create them from dev then you 
have all the changes to that point in your new branch.


#### How can you move changes from one branch to another in GIT?
Create a new branch from where you should have,
and then cherry pick the changes on the incorrect branch into the new branch.

You can then delete the bad branch, assuming you haven't
pushed it elsewhere and other changes have been made against it.


#### How does a VCS help with code reviews?
Start with a pull request
Pull requests are fundamental to how teams review and improve code on GitHub.
Evolve projects, propose new features, and discuss implementation details before changing your source code.

Make a change
Start a new feature or propose a change to existing code with a pull
request—a base for your team to coordinate details and refine your changes.


#### What is your favorite git command? Why?
git log --oneline

By default, the git log statement returns a full log entry for
each commit made to a repository. You can retrieve a list of 
commit IDs and their associated commit messages using the –oneline 
flag. We can see the commit IDs and the first line of the messages associated with a commit.


#### What does remote/local mean in Git? 
A local branch is a branch that only you (the local user) can see. 
It exists only on your local machine. A remote branch is a branch 
on a remote location (in most cases origin ). ... You can update your 
remote tracking branch to be in sync with the remote branch using git fetch or git pull .


### DevOps

#### Why is it good to use a package manager software?
A package manager is a programming language's tool to create project 
environments and easily import external dependencies. You don't have 
to reinvent the wheel and are able to make the most of the tools at 
your disposal. ... All this helps online repositories store your 
package and allows others to find your project

pl pip, npm


#### Why is it good to use a virtual environment for a project?
You can use any version of python you want for a specific environment without
having to worry about collisions (shoutout to my python 2.7 mac users!)

You can organize your packages much better and know exactly the packages 
you need to run your code incase someone else needs to run it on their machine

Your main python package directory does not get FLOODED with unnecessary python packages


### Networks

#### What kind of HTTP status codes do you know?
1xx informational response – the request was received, continuing process
2xx successful – the request was successfully received, understood, and accepted
3xx redirection – further action needs to be taken in order to complete the request
4xx client error – the request contains bad syntax or cannot be fulfilled
5xx server error – the server failed to fulfil an apparently valid request


#### What is a API?
Az API (angol rövidítés eredete application programming interface)
alatt egy olyan programozási interfészt, programozási felületet és
annak részletes dokumentációját értjük, amelynek segítségével egy 
rendszer egy másik programhoz (esetleg rendszerprogramhoz) csatlakozhat.
Ennek révén a másik programrendszer szolgáltatási használhatóak, anélkül,
hogy a program belső részleteit ismerni kellene. (Ellentétben az 
általános értelemben vett interfész fogalmával ahol az interfész az
adatok átadását-fogadását határozza meg, az API a másik program 
funkcionalitásainak használatát teszi lehetővé), Az API dokumentációjához 
tartozik a paraméterek pontos leírása is. A paraméterekkel lehetséges 
információkat átadni, illetve eredményeket átvenni. Az API-k használata
független a programnyelvtől (azaz az API segítségével meghívott program,
nem kell, hogy ugyanazon a nyelven íródjon, mint a hívó program). Tipikus 
API lehet pl. egy operációs rendszer szolgáltatásainak használata, egy
speciális feladatra írt függvény/eljárás-gyűjtemény használata (pl. gépek
és eszközök közötti kommunikáció)) vagy egy program funkcionalitásának
használata (pl. a Google Map funkciók használata saját programban)


#### What is REST API?
Representational State Transfer (REST) Application Programming Interface (API)

Adathozzáférés HTTP protokollon keresztül
CRUD műveletek adatforráson modelleken
HTTP metódusok segítségével (GET, POST, DELETE, PUT/PATCH)
(Általában) JSON formátumú kérések/válaszok

#### What is JSON? When to use?
JSON is typically used in two cases. One is to POST data to a web server. 
The other is a web server’s response to the client. Web servers may choose 
to use other formats, like XML, so don’t assume that every web server will use JSON.


#### What is TCP/IP? What layers does it define, what are they responsible for?
https://searchnetworking.techtarget.com/definition/TCP-IP

TCP/IP stands for Transmission Control Protocol/Internet Protocol and
is a suite of communication protocols used to interconnect network 
devices on the internet. TCP/IP is also used as a communications 
protocol in a private computer network (an intranet or extranet)

The 4 layers of the TCP/IP model
TCP/IP functionality is divided into four layers, each of which includes specific protocols:

The application layer provides applications with standardized data exchange.
Its protocols include HTTP, FTP, Post Office Protocol 3, Simple Mail Transfer 
Protocol and Simple Network Management Protocol. At the application layer,
the payload is the actual application data.

The transport layer is responsible for maintaining end-to-end communications 
across the network. TCP handles communications between hosts and provides flow control, 
multiplexing and reliability. The transport protocols include TCP and User Datagram 
Protocol, which is sometimes used instead of TCP for special purposes.

The network layer, also called the internet layer, deals with packets and connects 
independent networks to transport the packets across network boundaries. The network 
layer protocols are IP and Internet Control Message Protocol, which is used for error reporting.

The physical layer, also known as the network interface layer or data link layer, 
consists of protocols that operate only on a link -- the network component that 
interconnects nodes or hosts in the network. The protocols in this lowest layer 
include Ethernet for local area networks and Address Resolution Protocol.


#### What’s the difference between TCP and UDP?
https://www.lifesize.com/en/blog/tcp-vs-udp/
TCP is a connection-oriented protocol, whereas UDP is a
connectionless protocol. A key difference between TCP and 
UDP is speed, as TCP is comparatively slower than UDP. Overall, 
UDP is a much faster, simpler, and efficient protocol, however,
retransmission of lost data packets is only possible with TCP. 

Another notable discrepancy with TCP vs UDP is that TCP provides
an ordered delivery of data from user to server (and vice versa), 
whereas UDP is not dedicated to end-to-end communications, nor does
it check the readiness of the receiver (requiring fewer overheads and taking up less space).  


#### How does an HTTP Request look like? What are the most relevant HTTP header fields?
#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
HTTP header fields provide required information about the request or response, 
or about the object sent in the message body. There are four types of HTTP message headers:

General-header: These header fields have general 
applicability for both request and response messages.

Client Request-header: These header fields have 
applicability only for request messages.

Server Response-header: These header fields have 
applicability only for response messages.

Entity-header: These header fields define meta information
about the entity-body or, if no body is present, about the resource identified by the request.

pl request:
GET /search?q=test HTTP/2
Host: www.bing.com
User-Agent: curl/7.54.0 (- headers!)
Accept: */*

pl.In this example: response
the HTTP version is HTTP/1.1
the status code is 200
the reason phrase is OK


#### What is DNS? How does it work?
It represents a system of interconnected servers that store registered 
domain names and Internet Protocol (IP) addresses.
A DNS-nél elsődlegesen UDP-t használunk, mivel a TCP inicializálása időt
vesz igénybe, míg az UDP-nél már az első csomaggal elküldhetjük a teljes
kérést, és a válaszcsomagban már meg is kaphatjuk a választ.

Amikor a böngészőbe írunk egy adott domain nevet,
akkor, elkezdődik a folyamat, melyben a domain, IP címre kerül lefordításra.
Domain név – root name – google …………megkapjuk a konkrét információkat, a számítógép címét.

A DNS felépítése
A DNS egy hierarchikus rendszer, az internetre vagy magánhálózatra kapcsolódó 
számítógépek, szolgáltatások számára. A domainekhez információkat társít. 
Elsődleges funkciója az, hogy azokat a tartomány neveket, amelyek számunkra,
felhasználók számára értelmes kifejezések, azt a hálózati eszközök számára szám formátumú azonosítókká alakítsa.

A tartománynévrendszert szokták úgy emlegetni, mint az internet telefonkönyve,
ahol megtaláljuk a számunkra érthető nevek mellett, a számokból álló IP-címet.
Amikor a számítógépünk a hálózathoz kapcsolódik, akkor egy elérési címet, úgynevezett, IP-címet kap.

A tartományneveknek  van más célja is, ez pedig az egyszerűsítés.
A doménnevet  pl. https://hwellkft.hu/ sokkal könnyebb megjegyezni,
mint egy IP-címet, amely sok-sok számból áll. Ha legközelebb 
valamire választ szeretnénk kapni, már könnyen eszünkbe 
fog jutni az a domain név ahonnan az információt kereshetjük.
https://hwellkft.hu/marketing-szotar/dns


#### What is a web server?
A webkiszolgáló vagy webszerver egy olyan számítógép,
amelyik elérhetővé teszi a weboldalakat HTTP protokollon keresztül. 
A http webszerverekhez webböngészőkkel (pl. internet explorer, 
mozilla firefox, google chrome, stb.) lehet kapcsolódni. 
A böngésző letölti a weblap kódját tartalmazó fájlokat, 
képeket, videókat és egyéb médium anyagokat.

A dinamikus webszerverek nem csak a tárolt információt juttatják 
el a klienshez, hanem scripteket, programokat is futtatnak. 
Ilyenkor a szerveren futó modulok illetve a webszerver által 
meghívott CGI rutinok végzik el ezt a feladatot. A programrészletek 
legtöbbször, a HTML kódba vannak beágyazva és a webszerver-program 
hajtja ezeket végre.A nagyszámú egyidejű lekérések stabil kiszolgálásának
érdekében, a webszerverek nagy teljesítményű, speciális számítógépek 
kell legyenek. Ugyanakkor, a weblapok szünetmentes elérhetőségének 
biztosítása érdekében, a szervereknek robosztusnak kell lenniük, 
a meghibásodás esélye minimálisnak kell lennie.


#### Explain the client-server architecture.
Olyan architektúra, amelyen a kommunikációban résztvevő két fél
nem egyenrangú módon vesz részt, hanem dedikált szerepeket 
(szerver illetve kliens) töltenek be.

A jellemzően a kliens kezdeményezi, mégpedig azzal a céllal, hogy
valamilyen műveletet vagy lekérdezést végeztessen el a szerverrel.
A szerver a kérést megkapva elvégzi a megfelelő lépéseket, majd az
eredményt a kliens felé továbbítja. Bár az adatok a kommunikáció 
során értelemszerűen mindkét irányban áramolhatnak, a műveleteket 
elvégzését mindig a kliens kezdeményezi, és mindig a szerver 
hajtja végre - ennek megfordítására nincs mód.


#### What would you use a session for?
#### What would you use a cookie for?
The Session and cookies are used by different websites for storing 
user's data across different pages of the site. Both session and cookies 
are important as they keep track of the information provided by a visitor 
for different purposes. The main difference between both of them is that 
sessions are saved on the server-side, whereas cookies are saved on the 
user's browser or client-side.


Why and when to use Cookies?
Http is a stateless protocol; cookies allow us to track the state of 
the application using small files stored on the user’s computer. 
The path were the cookies are stored depends on the browser. Internet 
Explorer usually stores them in Temporal Internet Files folder. 
Personalizing the user experience – this is achieved by allowing users 
to select their preferences. The page requested that follow are 
personalized based on the set preferences in the cookies. 
Tracking the pages visited by a user.

Why and when to use Sessions?
To store important information such as the user id more securely on
the server where malicious users cannot temper with them. 
Sessions are used to pass values from one page to another.

It is also used when you want the alternative to cookies on browsers 
that do not support cookies, to store global variables in an efficient
and more secure way compared to passing them in the URL, developing
an application such as a shopping cart that has to 
temporary store information with a capacity larger than 4KB.


## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
Agile, Scrum, WaterFall, DevOps deployment.
https://www.synopsys.com/blogs/software-security/top-4-software-development-methodologies/


#### What are the SCRUM roles?
PO(Product Owner), Scrum Master, Scrum Team


#### What are the SCRUM ceremonies?
sprint planning, daily scrum, sprint review, and sprint retrospective.


#### What are the SCRUM artifacts?
Product Backlog
The product backlog is an ordered list of everything that is known 
to be needed in a product. It is constantly evolving and is never complete.

Sprint Backlog
The sprint backlog is a list of everything that the team commits to achieve
in a given sprint. Once created, no one can add to the sprint backlog except the development team. 

If the development team needs to drop an item from the sprint backlog, 
they must negotiate it with the Product Owner. During this negotiation, 
the Scrum Master should work with the development team and Product Owner to try 
to find ways to create some smaller increment of an item rather than drop it altogether.

Potentially Releasable Product Increment
At the end of every sprint, the team must complete a product increment that is
potentially releasable, meaning that meets their agreed-upon definition of done. 
(An example might be fully tested and fully approved.)


#### What is the main goal of a retrospective meeting?
cselekvési terv megalkotása
Tapasztalatok alapján fejlődés, javulás.


#### Explain, when would you recommend to use the waterfall methodology?
Waterfall is best for projects with concrete timelines and well-defined deliverables.
It’s a well-defined methodology that has been used in all business verticals.
It’s a tried and true methodology that is pretty straightforward and expectations are clear.
The methodology defines what you are building to a very detailed level at 
the beginning of the process. This makes setting deliverable dates,
start/end dates, milestone planning, as well as the team’s ability to track progress much easier.
Developers and testers can focus on writing code and writing test cases. 
They don’t have to work with stakeholders to determine what the product requirements are.
What the team is going to deliver is more predictable. Because the product 
requirements are documented and approved prior to the beginning of development, 
there is a commitment to deliver a specific set of features which makes the final product more predictable
module_web_with_python.md
module_web_with_python.md megjelenítése.
