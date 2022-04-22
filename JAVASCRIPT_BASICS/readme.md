# Getting started with Javascript 

## {via Strings}

### What is Javascript?


Javascript is the programming language of the internet. It is what makes websites interactive.


There are implementations of Javascript that run in lots of different environments (like node.js, for the console, or versions that live inside of game engines). There are also a lot of frameworks and libraries that extend its functionality (for example- p5.js, a thing many of you have probably interacted with in EMSII). These are useful things to keep in mind as tools for future projects! But we’ll be using plain old Javascript- often called ‘vanilla’ Javascript.


We are using this because it is hard to underestimate the reach of JS in 2019. Using it also means that you can immediately publish your work as an interactive website.


-


A nice thing about JS is there isn’t an installation. You already have a working and up-to-date version with any modern browser. I’ll be demoing in Firefox, but Chrome is essentially identical in functionality.


For those that stuck around for the evening quickstarts in HTML and CSS over the past few weeks, Javascript is the last bit of that puzzle. HTML is the "content" of the web (static content on websites). CSS is the "styling". Javascript is the "interaction".


-


Adding Javacript to your HTML page -


If you’ve done this before, or if you stayed for those quickstart nights on CSS and HTML, the structure of a website will look familiar to you.

```
<!DOCTYPE html>

<script>

javascript goes here

</script>

<style>

css goes here

</style>

<html>

        <head>

                <title>this is what is displayed in the webpage’s title bar</title>

        </head>

        <body>

this is the content of the page

        </body>

</html>
```

You can place JS directly between script tags, like this:

```
<script>

javascript goes here

</script>
```

Or have it search for an external JS page, like this:

```
<script src="yourfile.js"></script>
```

I’m prefer the second, as it is cleaner. But both are valid.


-



You could take a whole course on learning javascript, which is not what we’re going to be doing here. I’m going to assume some familiarity with some form of programming (p5.js or other artist’s tools count), so I’m not going to get into the logic of how programming languages work in a fundamental way. If anyone is totally fresh to this space, this will be pretty fast paced- please plan to come to my office hours tomorrow and we can run through some fundamentals a little slower.


-


Variables in JS (strings) -


We’re mostly going to be focused on strings and string manipulation. A ‘string’ is just a piece of text.


To define a string (or any other variable) in javascript, you use ‘var’. (You may also use ‘let’. They have a small difference we will talk about later.) Just saying ‘var str’ "initializes" a variable named str.


var str;


Think about variables as empty boxes that you can store things in. By typing ‘var str’, we’ve made an empty box (a variable) named ‘str’. Right now, it doesn’t have anything in it. If we ask for its contents, we will get ‘undefined’, which is javascripts way of saying "nothing is in this box".


We can put a value in the box by saying-


var str;

str = "some text we will do various things to";


We can also initialize the variable and put the value inside of it at the same time, by doing something like this;


var str = "some text we will do various things to";


Now, if we ask for the value of str, we will get  "some text we will do various things to".


In javascript, there are a lot of ways to ask for the value of a thing. The easiest way is using the console log, which keeps track of errors and logs as a program is running we can print anything to the console log by using


console.log(thingWeWantToPrint)


To get the value of our variable ‘str’ at any given point, we use:


console.log(str)


You should get used to using console.log() as a way to audit your code as it runs, as well as a way to see your output. You can see the console in your browser by opening "tools->developer->web console" (Firefox) or "view->developer->javascript console" (Chrome). Try opening it on a website you use normally to see what is logged.


-


Other types of variables / data-


In JS, variables are mutable, and they take their type from context. For example,


var variable; //undeclared variables are the type ‘undefined’. their value is also undefined

var string = "" //everything wrapped in quotes is treated as a string

var array = [] //wrapped in square brackets, treated as an array

var number = 1 //a number, treated as a number (no difference between floats and ints)

var number = 1.001 //a number, treated as a number (no difference between floats and ints)

var object = {} //wrapped in curly brackets, its an object

var boo = true //true or false means its a boolean


//(In javascript, anything after two slashes is a comment and is ignored by the code.)


Arrays are always wrapped in square brackets. They are basically lists. You can put whatever you want in them. We’ll look at them more later.


Numbers are just numbers. If wrapped in quotes, they are treated as literal text (you can’t do math on them if they are text.)


Objects are like dictionaries, with name:value pairs. They are wrapped in curly brackets. JSON is a type of object. Again, we’ll look at them later.


Boolean values are either true or false. We use them to do checks in logic. Also more on that later.


-


You can redefine a variable and change its type. (What you call a variable doesn’t mean anything- its just a way to reference it.) For instance;

 

var x = "hi" //x is a string

x = ["hi", "hey"] //x is now an array

x = 1 //x is now a number


You can check the type of a variable with the ‘typeof’ operator.


typeof x;

-


More reference on variable and data types; https://www.w3schools.com/js/js_datatypes.asp 


(Again, we’re mostly focused on strings)

-


Simple string manipulation-


Defining a string:


var str = "some text";


Redefining a string:


str = "some different text";



Adding two strings together:


var str = "some text";

var str2 = "some different text";


var str 3 = str + str2;


or-

str = str + str2;


or-

str2 = str + st2;


or-

str = str + " some text to add";


(all these are valid)


Adding a number to a string (valid - turns the number to a string):


var str = "some text" + 50;

var str = "some text" + 50 * 10; (try this)


Adding an array to a string:


var str = "some text";

var arr = ["whoa","does", "this", "work", 1, 2, 3, 5.55, []];

str = str + arr;


Getting a character at a point in a string:


        var str = "some text";

        var strChar = str[3]


Getting two characters at points in a string then adding them together


        var str = "some text";

        var strChars = str[3] + str[6] + str[8]


etc,, this all stacks, you get the idea


-


Built-in string methods-


There are a lot of methods in vanilla JS for dealing with text. This is partly because so much of the content of the internet is textual. They aren’t always intuitive (looking at you, math.random), but they are powerful!


var str = "some text we will do various things to";


str.length; //The length of a string, in characters. In general, 'positioning' in strings counts in characters. They start at 0.


Finding a string in a string:


str.indexOf("things"); //the first occurance of a string inside of a string. returns -1 if not found.


str.lastIndexOf("things"); //the last occurrence of a string inside of a string. returns -1 if not found.


str.indexOf("things", 5); //both have an optional second variable, which is where in the string to start looking.


str.lastIndexOf("things", 5); //when given a second parameter, lastIndexOf counts backwards from that point. for instance, if given '5' in this example, it would search backwards from "t emos".


str.search("locate"); //similar to indexOf, but takes regular expressions, and no second variable.


Getting parts of strings:


str.slice(start, end);   //str.slice() extracts a part of a string and returns the extracted part in a new string.


Takes 2 parameters: the start position, and the end position (end not included in the new string). Remember that counting in JS starts from 0. If you omit the second parameter, it will slice to the end of the string.


str = str.slice(0, 5);

// then str = "some";

str = str.slice(7);

// then str = "xt we will do various things to";


str.substr(start, length);   //very similar to str.slice(), except that the second parameter means the length of the string, not the end point. I prefer this one, but its a personal style choice.


str = str.slice(0, 5);

// then str = "some";

str = str.slice(7,6);

// then str = "xt we";


You may redefine your original string, or store the slice in a new variable, by saying something like:


var x = str.slice(0, 5);


Replacing parts in strings:


str.replace("value", "replacingThing");   //returns a new string with the ‘value’ replaced by the ‘replacingThing’.


By default, str.replace() only works on the first match, and is case sensitive. You change that with a Regex flag. We’ll look at Regex in a little bit. But for now:


str.replace(/value/i, "replacingThing");  //case insensitive

str.replace(/value/g, "replacingThing");  //global replace


Remember, you have to redefine your variable or store this string in a new variable to save it! It doesn’t edit the original string. For instance:


str = str.replace(/value/i, "replacingThing");  


Converting Case:


str.toUpperCase();   //returns a new string, all uppercase


str.toLowerCase();   //returns a new string, all lowercase (a great way to work with found text)


str = str.toLowerCase();


Remove whitespace:


str.trim();   //removes extra whitespace on both sides of a string, eg:


var str = "          hey          "

str = str.trim();


then str would be "hey"


Converting a string to an array:


str.split("what to split");   //turns a string into an array. useful for word and text manipulation. For example,


str.split(" ");   //splits on space

str.split(",");   //splits on commas

str.split("hi");   //splits on the word hi

str.split("");   //splits on every character

str.split();   //returns an array with the whole string in index [0].


We will talk more about arrays later on!


Complete reference on string methods: https://www.w3schools.com/jsref/jsref_obj_string.asp 

-


Logic -


This should look familiar to most of you, no matter what language you normally use or have worked with. The if/else conditional is pretty standard. In javascript, they basically look like this (please note they are lowercase in JS):


if (thingToBeTested){

//do stuff

}

else if (otherThingToBeTested) {

//do different stuff

}

else {

//do different stuff

}


In this example, our variables thingToBeTested and otherThingToBeTested need to be booleans (true or false) to work correctly. But we can build logic into these statements like this:

if (thingToBeTested == "a piece of text"){

//do stuff

}

else if (thingToBeTested.indexOf("hi") != -1) {

//do different stuff

}

else if (thingToBeTested.length > 10) {

//do different stuff

}

else {

//do different stuff

}


The conditional operators in Javascript are:


==                        equal to (be careful not to use just one =)

===                        equal to and equal type

!=                        not equal to

!==                        not equal to and not equal type

>                        greater than

<                        less than

>=                        greater than or equal to

<=                        less than or equal to

&&                        and

II                        or

!                        not


-


Loops -


Loops iterated a block of code a number of times. This is useful so we don’t have to type a thing a bunch of times, like:


x = x + 1

x = x + 1

x = x + 1


Instead, we write something like:


for (i = 0; i < 3; i++)

{  

x = x + i

}


Again, I’m assuming this is familiar to you. For loops are very useful with string manipulation though so I wanted to stick it in.


(There are also while loops, which are not as useful so I’m gonna skip em for now.)


-


Random numbers -


Random in JS is a little verbose, but basically;


Math.random() // returns a random number between 0 and 1 (a float).

 

Math.floor(value to floor) // rounds down to the closest integer (whole number).


You can combine them to create random whole numbers.


Math.floor(Math.random() * 10);   // returns a random integer from 0 to 9, by generating a random float between 0 and 1, multiplying that by 10, then rounding down to the closest whole number.


var randomChoice = Math.floor(Math.random() * 4000);   // the variable randomChoice is a random integer from 0 to 3999


Etc.


-


Making your own string methods with a function -


If you are new to programming, the idea of functions might not be familiar to you. Hopefully, you’ve used them in some capacity though. They are basically ways to make little blocks of logic that you can call at any point. All those methods like string.split() we looked at earlier are built-in functions. But you can make your own.


Functions are defined in Javascript with the function keyword, followed by a name, followed by parenthesis. Optional parameters (things you ‘pass in’) can go in the parenthesis, seperated by commas. The code to be executed goes in curly brackets.


function testFunction(parameter1,parameter2){

//code to do

}


The parameters passed in behave like ‘local variables’, which only exist inside the function. ‘parameter1’ can only be used inside the function.


Many functions do some stuff, then return a value with the return statement. For instance;


function testFunction(parameter1,parameter2){

var temp = parameter1.split(parameter2)

return temp;

}


Is a function that splits the string that is passed in with "parameter1" by the value "parameter2", then returns the variable temp (which is the array after splitting it).


You call a function by invoking its name with parentheses, like so:


testFunction("the string to split", " ");

var newArray= testFunction("the string to split", " "); //same thing, but storing the returned value


Making little functions that can operate on pieces of text is the heart of interesting text manipulation in Javascript.


-


Arrays -


Okay, I promised Arrays and here we are. The Array object in JS is basically a list that stores multiple values in a single variable. These values can be any type, including other arrays!


They look like this:


var arr = ["hey", "hi", 0, "what", ["whoa", "another", "array"], 100];


To access the value of an item in an array, you use this:


arr[0], with [0] being the position of the item you want the value of. The index starts at 0.


You can redefine an item in an array merely with the ‘=’ operator, like this.


        arr[1] = "yep";


Arrays are especially useful with for loops, where you can iterate over every item. This is great if you split a text up into an array with the .split() method, and want to, say, check what every array item is.  


for (i = 0; i < arr.length; i++)

{  

console.log(arr[i])

arr[i] = i + " " + arr;

}


There are a lot of cool array methods. They will be useful to us:


var arr = ["hey", "hi", "he"];

var arr2 = [0, 100, "yes"];


var x = arr.length;   // The length property returns the number of elements

var x = arr.sort();   // The sort() method sorts arrays

var x = arr.concat(arr2); //combines two arrays

var x = arr.includes(element, start) //sees if an array includes an element, and the optional index where to start looking. returns true or false

var x = arr.indexOf(element, start); //sees if an array includes an element, and the optional index where to start looking. returns the position where the element was found.

var x = arr.reverse(); //reverses the array, back to front

var x = arr.sort(); //sorts the array alphabetically. (Can take a function as a parameter too- for advanced folks maybe)

var x = arr.slice(start,end); // arr.slice(1,4) slices elements 1, 2, and 3 out of the array and puts them in the variable x.


And perhaps most importantly!


var x = arr.join(combiner) //Joins elements of an array into a string! The combiner is what is stuck in between elements. If left blank, it uses commas. An empty string "" is nothing. That and a space, " ", is common for our needs.


There is also:

arr.push(element) //adds an element to the end of array

arr.pop(element) //removes an element from the end of array


These add and remove elements from the end of an array. This changes the original array.


Arrays are one of the simplest ways to store a lot of data and use in generative text applications. For instance, if you wanted to make a mad-libs style generator:





All you would need to fill this in would be something like this:


var nouns = []

var adjectives = []

var verbs = []

var adverbs = []


And a Math.random() picker function. I’ll show you how you’d make something like this right now!


-


Debugging-


One thing that is both great and confusing about Javascript is that it is not a ‘typed’ language. Many programming languages have different ‘types’ of variables, which cannot be combined or used together without changing them from one to another. For instance, in python you can’t do ‘array’ operations on a string, or in C++ you can’t add an integer and a float number. This is not a problem in Javascript! You can do anything to whatever! You won’t get errors! But sometimes you get some weird results.


Common variable values that mean something got weird somewhere;

Undefined - A variable that has no value

Null - Nothing, doesn’t exist

NaN - Not a number, you’re trying to do a number thing on something that isn’t a number.


Additionally, your program might crash while it is running. This is often a semantic error, like an out of place bracket. The console will generally tell you what line of code it stopped on. You can then check this line in your text editor.


Here is a great list of common problems - feel free to scan over it, or you can always Google your specific error; https://www.w3schools.com/js/js_mistakes.asp
