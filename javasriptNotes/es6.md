# ES6
## Let
- unlike var, when using let, a variable with the same name can only be declared once. Strict Mode, which catches common coding misakes and unsafe action.
- "use strict" display x as undefined
- The let keyword behaves similarly, but with some extra features. When you declare a variable with the let keyword inside a block, statement, or expression, its scope is limited to that block, statement, or expression.

For example:

function checkScope() {
  "use strict";
  let i = "function scope";
  if (true) {
    let i = "block scope";
    console.log("Block scope i is: ", i);
  }
  console.log("Function scope i is: ", i);
  return i;
}

## Const Variable
- const is a constant variable. You can not change the value of a already declared variable
-The following will not work
const FAV_PET = "Cats";
FAV_PET = "Dogs";

- However, it is important to understand that objects (including arrays and functions) assigned to a variable using const are still mutable. Using the const declaration only prevents reassignment of the variable identifier.
```js
const s = [5, 7, 2];
function editInPlace() {
  // Using s = [2, 5, 7] would be invalid
  s[0] = 2;
  s[1] = 5;
  s[2] = 7;
}
editInPlace();
```

## Prevent Object Mutation
- As seen in the previous challenge, const declaration alone doesn't really protect your data from mutation. To ensure your data doesn't change, JavaScript provides a function Object.freeze to prevent data mutation.

- Once the object is frozen, you can no longer add, update, or delete properties from it. Any attempt at changing the object will be rejected without an error.
```js
let obj = {
  name:"FreeCodeCamp",
  review:"Awesome"
};
Object.freeze(obj);
obj.review = "bad";
obj.newProp = "Test";
console.log(obj); 

```
- The obj.review and obj.newProp assignments will result in errors, and the console will display the value { name: "FreeCodeCamp", review: "Awesome" }.

## Arrow Function
- In JavaScript, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions. We don't need to name these functions because we do not reuse them anywhere else.

```js
// Inline functions originally looked like this. 
const myFunc = function() {
  const myVar = "value";
  return myVar;
}
// ES6 turned them into an arrow function instead on anonomous function
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```
- When there is no function body, and only a return value, arrow function syntax allows you to omit the keyword return as well as the brackets surrounding the code. This helps simplify smaller functions into one-line statements:
```js
const myFunc = () => "value";

// This code will still return the string value by default.

