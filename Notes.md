# Data Types
* number
* boolean
* string
* object
* undefined - value has not been set yet
* null - explicit assertion that there "is no value"

###### if you are unsure you can always use typeof
```Node.js
console.log(typeof 10) \; // number
console.log(typeof "hello"); // string 
console.log(typeof function () {var x = 20;}); // function
```

# Type Comparisons and Conversions
* equality operator ==
* strict/precise equality operator === (meaning the value and type has to match)



```Node.js
console.log(234 == '234'); // true
console.log(234 === '234'); // false
```

# To check arguments to functions 
```Node.js
function fine(param) {
  if (param == null || param == undefined || param =='')
    throw new Error("Invalid Argument");
}

function better(param){
  if (!param)
    throw new Error("Invalid Argument");
 }
 ```
 
# Numbers
* numbers work like real number 
* Arithmetic operations (+,-,*,/,%) work on numbers as expected
* Dividing by Zero will return infinity or -infinity instead of crashing
* Use parseInt("") to convert string into Numbers(drops any decimal)
* Use parseFloat("") to convert string into Floats
```Node.js
var myData = 1; 
var myValue = 2; 
console.log(myData + 1); //2
console.log(myData / myValue); //0.5
console.log(myData * myValue); //2
console.log(myData - myValue); //-1
console.log(myData % 2); //1
console.log(myData /0); //Infinity

var a = "8";
console.log(32+8); //40
console.log(parseInt(a+32)); //832
var b = "1.5"
var b = "1.5"
console.log(parseInt(b)); //1
console.log(parseFloat(b));//1.5
console.log(parseInt(a)+parseFloat(b)); //9.5

//parseInt("Invalid value") will return NaN
console.log(parseInt("hello")); // NaN
```

# Boolean
* true or false
* default false value - false, 0, empty strings "", NaN, null, and undefined 
* default true value - all other value
```Node.js
console.log(true && true); // true 
console.log(true && false); // false 
console.log(true || false); // true 
console.log(false || false); // false 
console.log(!true); // false 
console.log(!false); // true 
```

# Strings 
* Sequences of Unicode characters
* String of length one represent character
* String can be in 'single quotes' or "double quotes"
* Use \' or \" to insert single or double quote within a string
```Node.js
console.log('Javascripts new feature.'); // Javascripts new features.
console.log("\'J\'A\'V\'A\' \"Script\""); // 'J'A'V'A' "Script"

var x = "Hello";
console.log(x.length); //5
console.log(x+" world!"); //Hello world!
```
* find the index of something by using .indexOf("");
* extract a substring from string using .substr(starting index, length of string to extract);// not including the last one
* extract a substring from string using .splice(starting index, ending index);
* split string into substrings using .split(""); //return array with elements being each substring
```Node.js
var s = "Hello".substr(0, 2);
var s1 = "World".slice(2, 4);
console.log(s); //he
console.log(s1); // rl

var s2 = "a,b,c,d,e".split(",");//['a','b','c','d','e']
```

# Object Literal Notation
```Node.js
//two ways to create objects
var o1 = new Object();
var o2 = {}; //preferred

//Example
//create object named 'car' with properties of enginee, model, gas
var car = {
  enginee: "v8",
  model: 2020,
  gas: "electric"
};
//check
console.log(car);
//There are three different ways to add properties
//add color
car.color = "blue";
//check
console.log(car);
//add number of seats
car["numSeats"] = 5;
//check
console.log(car);
//add safetyFeatures
var safetyFeatures = 'safetyFeatures';
car[safetyFeatures]=["seatbelts","airbags", "spare tire"];
//check
console.log(car);

//In order to remove a property use 'delete'
delete car.safetyFeatures;
//check
console.log(car);
```

# JSON - JavaScript Object Notation 
* Wrapping String in double quote is mandatory!
```Node.js
//This is VALID Object Literal Notation, but INVALID JASON:
var sudan = {
  "firstName": 'Honda', //JSON string require, "Honda"
  lastName: "Civic"      //Must wrap property name for JSON "lastName"
}
//This is a VALID JSON notation
var bmw = {
  "firstName": "Mini",
  "lastName": "Cooper"
}
```
# Arrays
```Node.js
//two ways to create an array
var arr1 = new Array();
var arr2 = []; //preferred

//check if a var is an array
Array.isArray(arr2); //true


var randomCarColors = []; 
randomCarColors.push("blue"); // add at the end 
console.log(randomCarColors); //["blue"] 

randomCarColors.unshift("white"); // add to the front
console.log(randomCarColors); //["white","blue"] 

// Arrays are zero index based: 
console.log(randomCarColors[0]); //["White"]

var arr = [1,2,3];//[1,2,3]
arr[arr.length] = 50; //[1,2,3,50]
arr[5] = 60;          //[1,2,3,,50,60]

//to delete you can use splice to specify the starting index and number of items to delete
arr.splice(2,3);[1,2,60]

//to insert and delete elements at the end of the array use 'push("")' and 'pop()'
//to insert and delete elements at the front of the array use 'unhift("")' and 'shift()'
//to return string from the array '.join()'
//to sort 'sort()'
//to iterate items in arrays, we can use the for loop or 'forEach()'
```

# Functions
* functions always return a value, if not explicit, it returns undefined
* anonymous functions - nameless functions
```Node.js
function functionName(){
  //function body;
  //optional return;
}

function greet(name){
  console.log("Greetings, " + name);
}
greet(); //Greetings, undefined
greet("John"); //Greetings, John
greet("John", "Bob", "Alex"); //Greetings, John

//nameless functions
var x = function(a,b){
  return a+b;
}
console.log(x(1,2));
```

# Regular Expression
* RegExp obj is used for matching text with pattern
* commonly used to validate text, and search through text
* regular expression literal consists of a pattern enclosed between /slashes/
* followed by the /slash/ will be a flag variable(s).
* Flag variable 'g' - global
* Flag variable 'i' - case insensitive
* Flag variable 'm' - multiline
* Flag variable 's' - single line(dotall)
* Flag variable 'u' - unicode
* Flag variable 'y' - sticky

* Token '+' - one or more
* Token '?' - optional 
* Token '*' - zero or more (combination of + and ?)
* Token '.' - it matches anything all, except a new line
* Token '\' - cancel anything/escapes. Or simply treat it as normal. 
* Token '\w' - matches all the words // has negation '\W'
* Token '\s' - matches all the white space // has negation '\S'
* Token '\w{x,y}' - x = minium chars in the word, y = maximum chars in the word

```Node.js
//Text we are going to use for the example
=======================================
||The fat cat ran down the street.    ||
||It was searching for a mouse to eat.||
=======================================
/at/g     //will highlight all the 'at' 
/t/gi     //will highlight all the 't', 'T' 
/e+/g     //will highlight all the 'e', 'ee', 'eee', 'ee...e' 
/e+a?/g   //will highlight all the 'e', 'e...e', 'ea', 'e...ea' 
/at*n*/g  //will highlight all the 'a', 'at', 'at...t', 'an', 'an...n'
/a./g     //will highlight all the 'aa', 'ab', 'ac', 'a.' and a followed by anything
/\./      //Will highlight all the '.' //backslash allows you to print all the special characters
/\w/      //Will highlight all the words (words and numbers)
/\W/      //Will highlihgt all the not words (white spaces and symbols)
/\s/      //Will highlight all the white space (no symbols)
/\S/      //Will highlight all the not white spaces (words and symbols)
/\w{3,5}/ //Will highlight all the words with lenght 3 to 5.
```
# Character grouping
