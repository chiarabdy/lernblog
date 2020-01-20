+++
title = "Typescript"
date = "2019-10-16"
pinned = false
draft = false
image = "/img/tsc.png"
+++
## Typescript:
is an open-source **object-oriented** language developed and maintained by **Microsoft**, licensed under **Apache 2** license. It is a **typed superset of Javascript** that compiles to plain JavaScript.

### Building tsc file
```js
function greeter(person) {
    return "Hello, " + person;
}

let user = "Jane User";

document.body.textContent = greeter(user);
```
To compile it
```js
tsc greeter.ts
```
### TypeScript Features
__Cross-Platform:__ TypeScript runs on any platform that JavaScript runs on. The TypeScript compiler can be
installed on any Operating System such as Windows, MacOS and Linux.<br>
__Object Oriented Language:__ TypeScript provides powerful features such as Classes, Interfaces, and Modules. You can write pure object-oriented code for client-side as well as server-side development.<br>
__Static type-checking:__ TypeScript uses static typing. This is done using type annotations. It helps type checking at compile time. Thus, you can find errors while typing the code without running your script each time. Additionally, using the type inference mechanism, if a variable is declared without a type, it will be inferred based on its value.<br>
__Optional Static Typing:__ TypeScript also allows optional static typing if you would rather use JavaScript's dynamic typing.<br>
__DOM Manipulation:__ Just like JavaScript, TypeScript can be used to manipulate the DOM for adding or removing elements.<br>
__ES 6 Features:__ TypeScript includes most features of planned ECMAScript 2015 (ES 6, 7) such as class, interface, Arrow functions etc.
## Type annotations 
JavaScript is not a typed language. It means we cannot specify the type of a variable such as number, string, boolean etc. However, TypeScript is a typed language, where we can specify the type of the variables, function parameters and object properties.
We can specify the type using ``:Type`` after the name of the variable, parameter or property. There can be a space after the colon. TypeScript includes all the primitive types of JavaScript- **number**, **string** and **boolean**.

The following example declares variables with different data types:
```js
var age: number = 32; // number variable
var name: string = "John";// string variable
var isUpdated: boolean = true;// Boolean variable
```
# TypeScript Data Type

## Number
__Example: TypeScript Number Type Variables__ <br>
```js
let first:number = 123; // number 
let second: number = 0x37CF;  // hexadecimal
let third:number=0o377 ;      // octal
let fourth: number = 0b111001;// binary  

console.log(first);  // 123 
console.log(second); // 14287
console.log(third);  // 255
console.log(fourth); // 57 
``` 
### Number Methods

Method                |Description
----------------------|:----------
toExponential()       |Returns the exponential notation in string format.
toFixed()             |Returns the fixed-point notation in string format.
toLocaleString()      |Converts the number into a local specific representation of the number.
toPrecision()         |Converts the number into a local specific representation of the number.
toString()            |Returns the string representation of the number in the specified base.
valueOf()             |Returns the primitive value of the number.

### toPrecison()
The toPrecision method returns the string representation in exponential or fixed-point to the specified precision.
__SYNTAX__
```js
chiar.toPrecision({precision})
```
```js
let chiar: number = 10.5679;

chiar.toPrecision(1); // returns 1e+1
chiar.toPrecision(2); // returns 11
chiar.toPrecision(3); // returns 10.6
chiar.toPrecision(4); // returns 10.57
```
### toString()
The toString method returns a string representation of the number in the specified base.
__SYNTAX__
```js
chiar.toString([radix])
```
```js
let chiar: number = 123;
chiar.toString(); // returns '123'
chiar.toString(2); // returns '1111011'
chiar.toString(4); // returns '1323'
chiar.toString(8); // returns '173'
chiar.toString(16); // returns '7b'
chiar.toString(36); // returns '3f'
```
###valueOf()
__SYNTAX__
```js
chiar.valueOf()
```

```js
let chiar = new Number(123);
console.log(chiar) //Output: a number object with value 123
console.log(chiar.valueOf()) //Output: 123
console.log(typeof num) //Output: object

let num2 = num.valueOf() 
console.log(num2) //Output: 123
console.log(typeof num2) //Output: number
```
## String
is a primitive data type that is used to store text data. String values are surrounded by single quotation marks or double quotation marks.
```js
let name:string = 'Chiar'; 
let age:number = 31;
// Pre-ES6 
let greeting: string = name + " from ROJAVA " + age; 

// Post-ES6
let greeting01: string = `${name} works in the ${age}`;

console.log(greeting);//Chiar from ROJAVA 31. 
console.log(greeting01);//Chiar from ROJAVA 31. 

```
### String Methods
Method                   | Description
-------------------------|:-----------
charAt()	             |Returns the character at the given index
concat()	             |Returns a combination of the two or more specified strings
indexOf()	             |Returns an index of first occurrence of the specified substring from a string (-1 if not found)
replace()	             |Replaces the matched substring with a new substring
split()	                 |Splits the string into substrings and returns an array
toUpperCase()	         |Converts all the characters of the string into upper case
toLowerCase()	         |Converts all the characters of the string into lower case
charCodeAt()	         |Returns a number that is the UTF-16 code unit value at the given index
codePointAt()	         |Returns a nonnegative integer Number that is the code point value of the UTF-16 encoded code point starting at the specified index
includes()	             |Checks whether a string includes another string
endsWith()	             |Checks whether a string ends with another string
LastIndexOf()	         |Returns the index of last occurrence of value in the string
localeCompare()	         |Checks whether a string comes before, after or is the same as the given string
match()	                 |Matches a regular expression against the given string
normalize()	             |Returns the Unicode Normalization Form of the given string.
padEnd()	             |Pads the end of the current string with the given string
padStart()	             |Pads the beginning of the current string with given string
repeat()	             |Returns a string consisting of the elements of the object repeated in the given times.
search()	             |Searches for a match between a regular expression and a string
slice()	                 |Returns a section of a string
startsWith()	         |Checks whether a string starts with another string
substr()	             |Returns a string beginning at the specified location and of the given characters
substring()	             |Returns a string between the two given indexes
toLocaleLowerCase()	     |Returns a lower case string while respecting current locale
toLocaleUpperCase()	     |Returns an upper case string while respecting current locale
trim()	                 |Trims the white space from beginning and end of string
trimLeft()	             |Trims the white space from left side of the string
trimRight()	             |Trims the white space from right side of the string