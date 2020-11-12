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
```
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
```
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
```
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
```
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
```
var s = "Hello".substr(0, 2);
var s1 = "World".slice(2, 4);
console.log(s); //he
console.log(s1); // rl

var s2 = "a,b,c,d,e".split(",");//['a','b','c','d','e']
```

# Objects
```
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

 
