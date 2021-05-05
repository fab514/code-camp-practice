## Parameters
- Parameters are variables that act as placeholders for the values when the function is called. 
- When a function is defined it is usually defined with one or more parameters. The values that are passed into a function are called arguments. 
```js
function testFun(a, b) {
    console.log(a + b);
}

testFun("Hello", "World"); // will show as HelloWorld in the console

```
## Math
- sum += + , difference - -=, product * *=, quotient / /=. Remainder % 5 % 2 = 1 
- increment of a variable ++i ++myvar, decrement of a variable --i, --myVar. 

## Escape sequences 
- Code	Output
\'	single quote
\"	double quote
\\	backslash
\n	newline
\r	carriage return
\t	tab
\b	word boundary
\f	form feed

## Concatenation
- Concatenate to strings. Remember to add spaces in the strings
```js 
var ourStr = "I come first. " + "I come second.";
// This will show as "I come first. I come second."

```
- You can also concatenate strings with varaibles
```js 
var myVar = "I come second!";
var ourStr = "I come first. " + myVar;
```
## array
- you can use .length on a string to find out how many values are in the string. The length starts with 0 
- you can also use .length on an array to find out how many values there are and mutate the array. 
- .pop pop a value at the end of an array
- .shift removes a value from the beginning of the array
- .unshift adds one or more parameters at the beginning of the array
- .push puts one or more parameters at the end of the array
- access an index in an array 
```js
var array = [50,60,70];
array[0];
var data = array[1];
```
- You can arrays within arrays 
```js 
var arr = [
  [1,2,3],
  [4,5,6],
  [7,8,9],
  [[10,11,12], 13, 14]
];
arr[3];
arr[3][0];
arr[3][0][1];
```

## Scope 
- global scope can reach all of your js
- local scope only reaches within the function

```js 
var globalVar = 2
function myFunction {
    var localVar = 4;
    console.log(localVar);
}
myFunction();
console.log(globalVar);
```

## Return a Value from a Function with Return

- We can pass values into a function with arguments. You can use a return statement to send a value back out of a function.

```js

function plusThree(num) {
  return num + 3;
}
var answer = plusThree(5); // answer has the value 8.

// plusThree takes an argument for num and returns a value equal to num + 3.
```

## Understanding Undefined Value returned from a Function

- A function can include the return statement but it does not have to. In the case that the function doesn't have a return statement, when you call it, the function processes the inner code but the returned value is undefined.

```js
var sum = 0;
function addSum(num) {
  sum = sum + num;
}
addSum(3);
// addSum is a function without a return statement. The function will change the global sum variable but the returned value of the function is undefined.

```
## Assignment with a return value

- We can take a retun value of a function and assign it to a variable. 

```js 
var changed = 0 
function plusThree(num) {
  return num + 3;
}
var answer = plusThree(5);

changed = plusThree(10);
```

- Everything on the right of the equal sign is resolved before value is assigned. 

## Queue a complex data structure where items are kept in order. 
```js 
// We are taking the nextInLine function and assigning it to an array that call this function.
function nextInLine(arr, item) { // takes in arguments or array and item
  arr.push(item); // use .push method to add a number to the end of an arr
  arr.shift(); // Takes off the first number in the array
  return item;
}

// Setup
var testArr = [1,2,3,4,5]; 

// Display code
// Stringify turns an array into a string.
console.log("Before: " + JSON.stringify(testArr)); // shows the array before the function is run
console.log(nextInLine(testArr, 6)); // array is called with the item value being 6. This is put into arr.push. 
console.log("After: " + JSON.stringify(testArr)); // shows the array after the function has been run. 

```

## Booleans
- Booleans are only true and false and do not use quotes. They're on off switches in code. 

## If statements 
- If statements are used to make desicisions in code. An if statement tells JS to execute a code with certain conditions. If the condition is true run the code if false don't run it. 
- if (condition is true) {
  statement is executed
}

```js 
function test (myCondition) {
  if (myCondition) { // When test is called with a value of true, the if statement evaluates myCondition to see if it is true or not.
     return "It was true"; // Since it is true, the function returns It was true.
  }
  return "It was false"; // When we call test with a value of false, myCondition is not true and the statement in the curly braces is not executed and the function returns It was false.
}
test(true);
test(false);
```

## Equality Comparisons
- == can show equality comparisons that uses boolean. 1 == 1 would be true 2 == 1 would be false. You can not use a single equal sign since that is used for declaring variables. 

```js
function equalityTest(myVal) {
  if (myVal == 10) { // if myVal condition is true then the first bracket will execute
     return "Equal";
  }
  return "Not Equal"; // if false the first bracket is skipped and this is ran. 
}
// Using type coersion a number and a string can return as true. 
// Strict Equality If you use a === then the type and the value must match. 1 = "1" is false.
1   ==  1 // True
1   ==  2 // False
1   == '1' // True
"3" ==  3 // True
```
- 3 == '3' returns true because JavaScript performs type conversion from string to number. 3 === '3' returns false because the types are different and type conversion is not performed.
  
- Note: In JavaScript, you can determine the type of a variable or a value with the typeof operator, as follows:

typeof 3
typeof '3'

typeof 3 returns the string number, and typeof '3' returns the string string.
```js
function compareEquality(a, b) {
  if (a === b) { 
    return "Equal";
  }
  return "Not Equal";
}
compareEquality(5, 5); // true
compareEquality(10, "10"); // false
```

- Inequality operator != not equal and strict inequality 
```js 
1 !=  2 // true
1 != "1" // false
1 != '1' // false
1 != true // false 
0 != false // false 

3 !==  3 // false
3 !== '3' // true
4 !==  3 // true

// Greater than first > second true
5   >  3 // true
7   > '3' // true
2   >  3 // false
'1' >  9 // false

function testGreaterThan(val) {
  if (val > 100) {  // Change this line
    return "Over 100";
  }

  if (val > 10) {  // Change this line
    return "Over 10";
  }

  return "10 or Under";
}

testGreaterThan(10);

// Greater then or equal too 
6   >=  6 // True
7   >= '3' // True
2   >=  3 // False
'7' >=  9 // False

// Less then <
2   < 5 // true
'3' < 7 // true
5   < 5 // false
'8' < 4 // false

// Less then or equal to <= 
4   <= 5 // true
'7' <= 7 // true
3   <= 2 // false
'8' <= 4 // false
```

## Comparisons with the Logical And Operator

- Sometimes you will need to test more than one thing at a time. The logical and operator (&&) returns true if and only if the operands to the left and right of it are true.

```js
if (num > 5 && num < 10) { // if both sides are true return yes
  return "Yes";
}
return "No";

```

- The logical or operator (||) returns true if either of the operands is true. Otherwise, it returns false.

```js 
function testLogicalOr(val) {

  if (val < 10 || val > 20) {
    return "Outside";
  }

  return "Inside";
}

testLogicalOr(15);
```
## if/else statements
- if the condition is true then the code is executed, if false and alternate block of code is executed

```js
function testElse(val) {
  var result = "";
  // Only change code below this line

  if (val > 5) {
    result = "Bigger than 5";
  } else {
    result = "5 or Smaller";
  }
 // Only change code above this line
  return result;
}

testElse(4);

```
## else if
- with multiple conditions that need to be addressed you can chain if statements together
- Order is important in if, else if statements.
- The function is executed from top to bottom so you will want to be careful of what statement comes first. If the first is true then execution will stop there. Changing the order will change the result

```js
function testElseIf(val) {
  if (val > 10) {
    return "Greater than 10";
  } else if (val < 5) {
    return "Smaller than 5";
  } else {
  return "Between 5 and 10";
  }
}

testElseIf(7);

```
- if/else statements can be chained together for complex logic. Here is pseudocode of multiple chained if / else if statements:

```js
function testSize(num) {
  
  if (num < 5) {
  return "Tiny"
} else if (num < 10) {
  return "Small"
} else if (num < 15) {
  return "Medium"
  } else if (num > 20) {
  return "Large"
} else if (num >= 20) {
  return "Huge"
} else {
  return "Change Me";
  }
}

testSize(7);

``` 
## Switch Statements

- If you have many options to choose from use switch statement. 
- A switch statement tests a value and can have many case statements which define several possible values. 
- Statements are executed from the first matched case value until a break is encoutered. 
- case values use strict equality (===). If the break is omitted the the next statement will be executed.

```js
function caseInSwitch(val) {
  var answer = "";
  // Write a switch statement which tests val and sets answer for the following conditions:
  // You can also add a default statement if there are no matching statements.
  switch (val) {
      case 1:
          answer = "alpha" 
          break
      case 2:
          answer = "beta"          
          break
      case 3:
          answer = "gamma"
          break
      case 4:
          answer = "delta"
          break
      default: 
          answer = "echo" 
          break
  }

  return answer;
}

caseInSwitch(4);

```
## Multiple identical options in switch statements
- If break statement is omitted from the switch statements case, the following case statements are executed until a break is encountered. 
- You can list multiple cases before the break and they will run as the same result. 
- Switch statements are easier to write when there are many options instead of if/else statements

```js
function sequentialSizes(val) {
  var answer = "";
  // Only change code below this line
  switch(val) { // 1, 2 and 3 will show the same result "Low"
    case 1: 
    case 2: 
    case 3:
      answer = "Low"
      break
    case 4: 
    case 5: 
    case 6:
      answer = "Mid"
      break
    case 7: 
    case 8: 
    case 9:
      answer = "High"
      break
  }

  // Only change code above this line
  return answer;
}

sequentialSizes(1);

function chainToSwitch(val) {
  var answer = "";
  // Only change code below this line

  switch (val) {
    case "bob":
      answer = "Marley";
      break;
    case 42: 
      answer = "The Answer";
      break;
    case 1: 
      answer = "There is no #1";
      break;
    case 99: 
      answer = "Missed me by this much!";
      break;
    case 7: 
    answer = "Ate Nine";
    break;
  }

  // Only change code above this line
  return answer;
}

chainToSwitch(7);
```

## Returning Boolean Values from Functions
- All comparison operators return a boolean. 
- You can use an if/else statement do a comparison
```js 
function isEqual(a,b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
// But there's a better way to do this. Since === returns true or false, we can return the result of the comparison:
function isEqual(a,b) {
  a === b;
}
```
## Return 
- when a return statement is reached the execution of the current function stops and control returns to the calling location. Things underneith the return will not run. 
```js
function myFun() {
  console.log("Hello");
  return "World";
  console.log("byebye") // This will not show because it is under the return.
}
myFun();

function abTest(a, b) {

   if (a < 0 || b < 0) {
     return undefined;
   } 

  return Math.round(Math.pow(Math.sqrt(a) + Math.sqrt(b), 2));
}

abTest(2,2);
// Math.round() function returns the value of a number rounded to the nearest interger. 
// Math.pow() function returns the base to the exponent power.
// Math.sqrt() function returns the square root of a number. 
```
## Object
- Objects are similar to arrays, in arrays you access and modify data by using index; for an object you access and modify data through properties. 
- Objects are useful in storing data in a structured way and can represent real world objects, like a cat. 

```js
var cat = { // make sure to use commas
  "name": "Whiskers",
  "legs": 4, 
  tails: 1, // for single words you can omit the quotes, JS will read them as a string.
  "enemies": ["Water", "Dogs"] // you can nest an array into an object
};
```
- Two ways to access an object, using [] similar to an array or, using a dot notation if you know the name of the property you would like to access.
- Second way to acess the properties in an object is bracket notation []. If the property you're trying to access has a space you need to use bracket notation.
- You can use bracket notation on single words.
- Accessing a property that is stored as a value of a variable, useful for iterating through objects properties or accessing a lookup table
```js
// dot notation
var testObj = {
  "hat": "ballcap",
  "shirt": "jersey",
  "shoes": "cleats"
};
var hatValue = testObj.hat; // returns "baseball" 
var shirtValue = testObj.shirt; // returns "cleats"
// bracket notation

var testObj = {
  "an entree": "hamburger",
  "my side": "veggies",
  "the drink": "water"
};

var entreeValue = testObj["an entree"];
var drinkValue = testObj["the drink"];   

// accesing a stored value
var dogs = {
  Fido: "Mutt",  Hunter: "Doberman",  Snoopie: "Beagle"
};
var myDog = "Hunter";
var myBreed = dogs[myDog];
console.log(myBreed); // Should return as a doberman

// another way of accessing a stored value
var someObj = {
  propName: "John"
};
function propPrefix(str) {
  var s = "prop";
  return s + str;
}
var someProp = propPrefix("Name"); // should show the value of the string propName
console.log(someObj[someProp]); // teh string John should show in the console
// do not use quotes around the variable name when using the access property. 
```


- After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.
```js
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.name = "Happy Camper"; // instead of getting Camper, we'll get his new name, Happy Camper.
// or ourDog["name"] = "Happy Camper"; 
```
## Adding and deleting properties to a JS object
- You can add new properties to existing objects the same way you can modify them. 
- Here's how we would add a bark property to ourDog:
ourDog.bark = "bow-wow"; or ourDog["bark"] = "bow-wow";
- You can also delete properties off of an object. 
delete ourDog.bark
```js
// adding a new property
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.bark = "bow-wow";
// deleting a property
var ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"],
  "bark": "bow-wow"
};

delete ourDog.bark; // bark property will be removed from the object
```
## Using objects for lookups
- You can use anobject to lookupvalues rather than a switch statement or if/else chain. This is most useful when you know that your input data is limited to a certain range.
```js
var alpha = {
  1:"Z",
  2:"Y",
  3:"X",
  4:"W",
  ...
  24:"C",
  25:"B",
  26:"A"
};
alpha[2]; // will return as "Y"
alpha[24]; // will return as "C"

var value = 2; // This will also show as "Y"
alpha[value];
```
## Testing objects for properties
- You can check if the property of a given object exists or not. 
- We can use the <strong>.hasOwnProperty(propname)</strong> method of objects to determine if the object has the given property name. 
- .hasOwnProperty returns a boolean(t/f) if the property is found or not. 
```js
var myObj = {
  top: "hat",
  bottom: "pants"
};
myObj.hasOwnProperty("top"); // true
myObj.hasOwnProperty("middle"); // false
```

## Manipulating complex objects
- A javascript object is a way to handle flexible data. You can store data in a flexible <strong>Data Structure</strong>.
- They can contain any combination of strings, numbers, booleans, arrays, functions and objects. 
- myMusic function has 2 objects inside which carries metadata about the object. 
```js
var myMusic = [
  {
    "artist": "Billy Joel",
    "title": "Piano Man",
    "release_year": 1973,
    "formats": [
      "CD",
      "8T",
      "LP"
    ],
    "gold": true
  }, //make sure to put a comma between every object. 
  {
  "artist": "Daft Punk",
  "title": "Homework",
  "release_year": 1997,
  "formats": [ 
    "CD",
    "Cassette",
    "LP"
  ],
  "gold": true
}
];
```
## Accessing Nested Objects
- subproperties of objects can be accessed by chaing together the dot or bracket notation. 
- If there is a space between words such as "top drawer" would need the bracket notation.
```js
// Here is a nested object:

var ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": { 
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};
ourStorage.cabinet["top drawer"].folder2; // will show the string "strings"
ourStorage.desk.drawer; // will show the string "stapler"
```
## Accessing nested arrays 
- Objects can contain nested objects or nested arrays. You can access nested objects using bracket notation and can be chained to access nested arrays. 
```js
var myPlants = [
  {
    type: "flowers",
    list: [
      "rose",
      "tulip",
      "dandelion"
    ]
  },
  {
    type: "trees",
    list: [
      "fir",
      "pine",
      "birch"
    ]
  }
];

var secondTree = myPlants[1].list[1]; // This will show "pine"

```
## While Loops
- You can run the same code multiple times by using a loop. 
- A while loop runs while a specified condition is true and stops once that condition is no longer true.

```js
var ourArray = [];
var i = 0;
while(i < 5) {
  ourArray.push(i);
  i++;
}
```
## For Loops
- For loops is the most common js loop because it runs a specific amount of times. 
- for (a; b; c) a is the initializing statement, b is the condition statement, c is the final expression. 
- Initializing statement is only run once when the loop starts. Used to setup and define the loop variable.
- Condition statement is evaluated at the beginning of every loop iteration and will continue as long as it shows true. If the statement is false at the beginning of the iteration the loop will stop executing. If condition starts false then the loop will not execute.
- The final expression is executed at the end of each loop iteration, prior to the next condition check and is usually used to increment or decrement your loop counter.

- In the following example we initialize with i = 0 and iterate while our condition i < 5 is true. We'll increment i by 1 in each loop iteration with i++ as our final expression.

var ourArray = [];
for (var i = 0; i < 5; i++) { // (a; b; c)
  ourArray.push(i);
}

ourArray will now have the value [0,1,2,3,4].

## Iterate Odd Numbers With a For Loop

- For loops don't have to iterate one at a time. By changing our final-expression, we can count by even numbers.

- We'll start at i = 0 and loop while i < 10. We'll increment i by 2 each loop with i += 2.

var ourArray = [];
for (var i = 0; i < 10; i += 2) {
  ourArray.push(i);
}

ourArray will now contain [0,2,4,6,8]. Let's change our initialization so we can count by odd numbers.

## Count Backwards With a For Loop

A for loop can also count backwards, so long as we can define the right conditions.

In order to decrement by two each iteration, we'll need to change our initialization, condition, and final expression.

We'll start at i = 10 and loop while i > 0. We'll decrement i by 2 each loop with i -= 2.

var ourArray = [];
for (var i = 10; i > 0; i -= 2) {
  ourArray.push(i);
}

ourArray will now contain [10,8,6,4,2]. Let's change our initialization and final expression so we can count backwards by twos to create an array of descending odd numbers.

## Iterate Through an Array with a For Loop

A common task in JavaScript is to iterate through the contents of an array. One way to do that is with a for loop. This code will output each element of the array arr to the console:

var arr = [10, 9, 8, 7, 6];
for (var i = 0; i < arr.length; i++) {
   console.log(arr[i]);
}

Remember that arrays have zero-based indexing, which means the last index of the array is length - 1. Our condition for this loop is i < arr.length, which stops the loop when i is equal to length. In this case the last iteration is i === 4 i.e. when i becomes equal to arr.length - 1 and outputs 6 to the console. Then i increases to 5, and the loop terminates because i < arr.length is false.
// Setup
var myArr = [ 2, 3, 4, 5, 6];

var total = 0
for (var i = 0; i < myArr.length; i++) {
  total += myArr[i];
}
console.log(total) // should add up to 20

## Nesting for Loops
- If you have a multi-dimensional array you can use the same logic as the prior waypoint to loop through both the array and any sub-arrays
- This output each sub-element in arr one at a time. 


```js
function multiplyAll(arr) {
  var product = 1;
  for (var i=0; i < arr.length; i++) {
    for (var j=0; j < arr[i].length; j++) {
      product *= arr[i][j]; // multiply the nested arrays within the outer array.
    }
  }
  return product;
}

multiplyAll([[1,2],[3,4],[5,6,7]]);// In the inner loop we are checking .length of arr[i], since arr[i] is itself an array. 
```
## do...while loop
- It is called the do while loop because it will first do one pass of the code inside of the loop no matter what, then continue to run the loop while the specified condition is true.

```js 
// Setup
var myArray = [];
var i = 10;

 do {
  myArray.push(i); // will already run this whether true or false
  i++;
} while (i < 5) // this is a false statement so the loop will stop running. 
// console will show 11[10]
```
## Replace Loops using Recursion
- Recursion is the concept that a a function can be expressed in terms of itself. 
- Recursion breaks a complex problem into small parts and loop over those parts
- Two main parts. A terminating condition (base case): causing the function not to be called again. Recursive Case: part that calls itself.
```js
  function multiply(arr, n) {
    if (n <= 0) { // terminating condition 
      return 1;
    } else {
      return multiply(arr, n - 1) * arr[n - 1]; // Recursive case (calls itself)
    }
  }

  ```
  ## Generate random Fractions with JS
  - Random numbers are useful for creating random behavior. 
  - Math.random() function generates a random decimal number between 0(inclusive) and not quite 1(exclusive). Math.random can return 0 but never return 1
  - Function calls are resolved before the return executes so we can return the Math.random() function.
```js
  function randomFraction {
      return Math.random();
  }
  ```
  ## Generate a random whole number
  - Use Math.random() to generate a random decimal.
  - Multiply that decimal by 20 (or +1 over your max number)
  - Use Math.floor to round the number down to the nearest whole number. 
  - Remember Math.random never reaches to 1 so we can not reach 20 so this will generate a random number between 0 and 19
  ```js
  Math.floor(Math.random() * 20);
  ```
  ## Generate Random whole numbers within a range
  - Instead of generating a random number between zero and a given number the random number can fall in a range. 
  - We use min and max
  ```js
  function randomRange(myMin, myMax) {
    return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin;
  }
  ```
  ### Code Explanation

    - Math.random() generates our random number between 0 and ≈ 0.9.
    - Before multiplying it, it resolves the part between parenthesis (myMax - myMin + 1) because of the grouping operator ( ).
    - The result of that multiplication is followed by adding myMin and then “rounded” to the largest integer less than or equal to it (eg: 9.9 would result in 9)

- If the values were myMin = 1, myMax= 10, one result could be the following:

    Math.random() = 0.8244326990411024
    (myMax - myMin + 1) = 10 - 1 + 1 -> 10
    a * b = 8.244326990411024
    c + myMin = 9.244326990411024
    Math.floor(9.244326990411024) = 9

    ## Using the parseInt Function
    - the parseInt("007");
    - The above function converts the string 007 to the interger 7. 
    - If the first character in the string can't be converted into a number, then it returns NaN (Not a Number). 

    ```js
    // Use parseInt() in the convertToInteger function so it converts the input string str into an integer, and returns it.
    function convertToInteger(str) {
      return parseInt(str)
    }
    
    convertToInteger("56");

  // The above function converts the string 007 to the integer 7. If the first character in the string can't be converted into a number, then it returns NaN.
    var a = parseInt("007");

  ```
  - The parseInt function can be used with a radix. The radix is the base of the number in the string
  - common radix is 10 0-9, 2 0-1 binary, octal 0-7, hexidecimal 0-F

  ```js
  function convertToInteger(str) {
    return parseInt(str, 2)
  }
  convertToInteger("10011"); 
  ```
## Use cpnditional (ternary) operator
- The conditional operator(ternary operater), can be used as a one line if-else expression
- The syntax is a ? b : c where a is the condition, b is the code to run when condition is true, and c is the code to run if the condition returns false.
```js
function findGreater(a, b) {
  if(a > b) {
    return "a is greater";
  }
  else {
    return "b is greater";
  }
}
// can be re-written using a conditional operator
function findGreater(a, b) {
  return a > b ? "a is greater" : "b is greater";
}
```
## Multiple Conditional (ternary) operators
- You can chain conditional operators together to check for multiple conditions. 
```js
function findGreaterOrEqual(a, b) {
  if (a === b) {
    return "a and b are equal";
  }
  else if (a > b) {
    return "a is greater";
  }
  else {
    return "b is greater";
  }
}
// Rewrite the above if-else statement to a ternary operator
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" 
    : (a > b) ? "a is greater" 
    : "b is greater";
}
```
## Recursion to create countdown

- Complex function that returns an array consecutive intergers from 1 - passed number
- There will be a base case. The base case tells the recursive function when it no longer needs to be called (loop)
- The return value is already know.
- There will be another recursive function which executes the original function with different arguments
- ex recursive function that returns an array from [1-n]

```js
function countup(n) {
  if (n < 1) {
    return [];
  } else {
    const countArray = countup(n - 1);
    countArray.push(n);
    return countArray;
  }
}
console.log(countup(5));
// console value will show [1, 2, 3, 4, 5]
// we use n - 1 because countArray.push runs last after the recursive call has returned. When n is pushed into the array it will return [1, 2...]

// .unshift will add one or more elements to the beginning of the array and returns a new length
function countdown(n){
  if (n < 1) {
    return [];
  } else {
    const arr = countdown(n - 1);
    arr.unshift(n);
    return arr;
  }
}

// need help!
function rangeOfNumbers(startNum, endNum) {
  if (endNum - startNum === 0) {
    return [startNum];
  } else {
    var numbers = rangeOfNumbers(startNum, endNum - 1);
    numbers.push(endNum);
    return numbers;
  }
}




















