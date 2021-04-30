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




