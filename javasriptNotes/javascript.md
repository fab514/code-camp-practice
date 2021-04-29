## Parameters
- Parameters are variables that act as placeholders for the values when the function is called. 
- When a function is defined it is usually defined with one or more parameters. The values that are passed into a function are called arguments. 

```js
function testFun(a, b) {
    console.log(a + b);
}

testFun("Hello", "World");

// will show as HelloWorld in the console.

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
- you can use .length on a string to find out how many values are in the string. The length starts with 0. 
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
