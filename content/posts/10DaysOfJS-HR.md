+++
title = "10 Days of JS"
date = "2019-09-06"
draft = false
pinned = false
image = "/img/hackerrank.png"
+++
# Overview: 10 Days of JavaScript

    This series focuses on learning and practicing JavaScript. Each challenge comes with a tutorial article, and you 
    can view these articles by clicking either the Topics tab along the top or the article icon in the right-hand menu.
## Day 0: Hello, World!
A greeting function is provided for you in the editor below. It has one parameter, . Perform the following tasks to complete this challenge:
### Task
1. Use console.log() to print Hello, World! on a new line in the console, which is also known as stdout or standard output. The code for this portion of the task is already provided in the editor.
2. Use console.log() to print the contents of (i.e., the argument passed to main).

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day00/helloWorld.js)

## Day 0: Data Types
### Task
Variables named **firstInteger**, **firstDecimal**, and **firstString** are declared for you in the editor below. You must use the **+**  operator to perform the following sequence of operations:

1. Convert **secondInteger** to an integer (Number type), then sum it with **firstInteger** and print the result on a new line using console.log.
2. Convert **seconDecimal** to an floating-point number (Number type), then sum it with **firstDecimal** and print the result on a new line using console.log.
3. Print the concatenation of **firstString** and **secondString** on a new line using console.log. Note that **firstSring**  must be printed first.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day00/dataTypes.js)

## Day 01: Arithmetic Operators
### Task
Complete the following functions in the editor below:
1. getArea(length, width): Calculate and return the area of a rectangle having sides **length** and **width** .
2. getPerimeter(length, width): Calculate and return the perimeter of a rectangle having sides **length** and **width** .
The values returned by these functions are printed to stdout by locked stub code in the editor.
### Explanation 0
* The area of the rectangle is **length** x **width** = 4 x 4.5 = 13.5 .
* The perimeter of the rectangle is 2.(**length** + **width**) = 2.(3 + 4.5) = 15.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day01/arithmetic.js)
## Day 01: Functions
### Task
Implement a function named factorial that has one parameter: an integer,**n** . It must return the value of **n**! (i.e., n factorial).
**Problem**
* A integer of value n is provided
* 1 ≤ n ≤ 10
* Output the factorial value of n (n!, 4! = 4 x 3 x 2 x 1 = 24)

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day01/Functions.js)

## Day 01: Let and Const
### Task
* Declare a constant variable,**PI** , and assign it the value Math.PI. You will not pass this challenge unless the variable is declared as a constant and named PI (uppercase).
* Read a number,**r** , denoting the radius of a circle from stdin.
* Use **PI** and **r** to calculate the **area** and **perimeter** of a circle having radius .
* Print **area** as the first line of output and print **perimeter** as the second line of output.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day01/letAndConst.js)

## Day 2: Conditional Statements: If-Else
### Task
Complete the getGrade(score) function in the editor. It has one parameter: an integer,**score** , denoting the number of points Julia earned on an exam. It must return the letter corresponding to her **grade** according to the following rules:

    If 25 < score <= 30, then grade = A.
    If 20 < score <= 25, then grade = B.
    If 15 < score <= 20, then grade = C.
    If 10 < score <= 15, then grade = D.
    If 5 < score <= 10, then grade = E.
    If 0 <= score <= 5, then grade = F.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day02/If-Else-Statements.js)

## Day 2: Conditional Statements: Switch
### Task:
Complete the getLetter(s) function in the editor. It has one parameter: a string, **s**, consisting of lowercase English alphabetic letters (i.e., a through z). It must return A, B, C, or D depending on the following criteria:

If the first character in string **s** is in the set {a ,e ,i ,o ,u } then return A.
If the first character in string **s** is in the set {b,c ,d ,f ,g } then return B.
If the first character in string **s** is in the set {h ,j ,k ,l ,m } then return C.
If the first character in string **s** is in the set {n ,p ,q ,r ,s , t , v, w, x,y, z}, then return D.
Hint: You can get the letter at some index  in  using the syntax s[i] or s.charAt(i)

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day02/ conditionalStatementsSwitch.js)

## Day 2: Loops
### Task
    Complete the vowelsAndConsonants function in the editor below. It has one parameter, a string,**s**, consisting of lowercase English alphabetic letters (i.e., a through z). The function must do the following:

1. First, print each vowel in **s** on a new line. The English vowels are a, e, i, o, and u, and each vowel must be printed in the same order as it appeared in **s**.
2. Second, print each consonant (i.e., non-vowel) in **s** on a new line in the same order as it appeared in **s**.
### Explanation
**Observe the following:**
    Each letter is printed on a new line.
    Then the vowels are printed in the same order as they appeared in .
    Then the consonants are printed in the same order as they appeared in .

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day02/loops.js)

## Day 3: Arrays
### Task 
Complete the getSecondLargest function in the editor below. It has one parameter: an array,**nums** , of **n** numbers. The function must find and return the second largest number in **nums**.

### Explanation
Given the array **nums = [2,3,6,6,5] , we see that the largest value in the array is 6 and the second largest value is 5. Thus, we return 5 as our answer.

* Return the second largest number in the array.
* @param {Number[]} nums - An array of numbers.
* @return {Number} The second largest number in the array.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day03/array.js)
## Day 3: Throw
### Task
Complete the isPositive function below. It has one integer parameter, . If the value of  is positive, it must return the string YES. Otherwise, it must throw an Error according to the following rules:

If **a** is 0, throw an Error with **message -Zero Error**.
If **a** is negative, throw an Error with **message - Negative Error**.

* Complete the isPositive function.
* If 'a' is positive, return "YES".
* If 'a' is 0, throw an Error with the message "Zero Error"
* If 'a' is negative, throw an Error with the message "Negative Error"

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day03/throw.js)

## Day 3: 
### Task
Complete the reverseString function; it has one parameter,**s** . You must perform the following actions:

1. Try to reverse string **s** using the split, reverse, and join methods.
2. If an exception is thrown, catch it and print the contents of the exception's **message** on a new line.
3. Print **s** on a new line. If no exception was thrown, then this should be the reversed string; if an exception was thrown, this should be the original string.
### Output Format

You must write two print statements using console.log():

* Print the contents of a caught exception's **message** on a new line. If no exception was thrown, this line should not be printed.
* Print **s** on a new line. If no exception was thrown, then this should be the reversed string; if an exception was thrown, this should be the original string.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day03/try-catch-finally.js)

## Day 4: Create a Rectangle Object
### Task
Complete the function in the editor. It has two parameters:**a**  and **b**. It must return an object modeling a rectangle that has the following properties:

* length: This value is equal to **a**.
* width: This value is equal to **b**.
* perimeter: This value is equal to **2**.(a +b)
* area: This value is equal to **a.b**

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day04/create-rectangle-object.js)

## Day 4: Count Objects
### Task
Complete the function in the editor. It has one parameter: an array,**a** , of objects. Each object in the array has two integer properties denoted by **x** and **y**. The function must return a count of all such objects **o** in array **a** that satisfy **o.x==o.y** .

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day04/count-objects.js)

## Day 4: Classes
### Task

Create a Polygon class that has the following properties:

* A constructor that takes an array of integer values describing the lengths of the polygon's sides.
* A perimeter() method that returns the polygon's perimeter.
Locked code in the editor tests the Polygon constructor and the perimeter method.

__Note:__ The perimeter method must be lowercase and spelled correctly.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day04/classes.js)

## Day 5: Inheritance
### Task

* Add an area method to Rectangle's prototype.
* Create a Square class that satisfies the following:
    1. It is a subclass of Rectangle.
    2. It contains a constructor and no other methods.
    3. It can use the Rectangle class' area method to print the         area of a Square object.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day05/inheritance.js)

## Day 5: Template Literals
### Task

The code in the editor has a tagged template literal that passes the area and perimeter of a rectangle to a tag function named sides. Recall that the first argument of a tag function is an array of string literals from the template, and the subsequent values are the template's respective expression values.

**Complete the function in the editor so that it does the following:**

* Finds the initial values of **s1**  and **s2** by plugging the area and perimeter values into the formula:
where **A** is the rectangle's area and **P** is its perimeter.
* Creates an array consisting of **s1** and **s2** and sorts it in ascending order.
* Returns the sorted array.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day05/template-literals.js)

## Day 5: Arrow Functions
### Task
Complete the function in the editor. It has one parameter: an **array**, **nums**. It must iterate through the array performing one of the following actions on each element:

* If the element is even, multiply the element by **2**.
* If the element is odd, multiply the element by **3**.
The function must then return the modified array.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day05/arrow-functions.js)

## Day 6: Bitwise Operators
### Task
We define **s** to be a sequence of distinct sequential integers from **1** to ; in other words, **S={1,2,3,...,n}**. We want to know the maximum bitwise AND value of any two integers, **a** and **b** (where **a>b**), in sequence **s** that is also less than a given integer,**k** .

* Complete the function in the editor so that given **n** and **k**, it returns the maximum **a&b < k**.

__Note:__ The  symbol represents the bitwise AND operator.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day06/bitwise-operators.js)

## Day 6: Javascript Dates
Given a date string,**dateString** , in the format `MM/DD/YYYY`, find and return the day name for that date. Each day name must be one of the following strings: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, or Saturday. For example, the day name for the date 12/07/2016 is Wednesday.

### Instructions:
The function is called for the following **d=2** dates:

* The date 10/11/2009 was a Sunday, so we return Sunday.
* The date 11/10/2010 was a Wednesday, so we return Wednesda

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day06/dates.js)

## Day 7: Regular Expressions!
Complete the function in the editor below by returning a RegExp object,**re** , that matches any string **s** that begins and ends with the same vowel. Recall that the English vowels are a, e, i, o, and u.

### Instructions:
    Declare a RegExp object variable named 're'
    It must match a string that starts and ends with the same vowel (i.e., {a, e, i, o, u}

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day07/r-expressions.js)


## Day7: Regular Expressions II
### Task

Complete the function in the editor below by returning a RegExp object, **re**, that matches any string **s** satisfying both of the following conditions:

* String **s** starts with the prefix Mr., Mrs., Ms., Dr., or Er.
* The remainder of string **s** (i.e., the rest of the string after the prefix) consists of one or more upper and/or lowercase English alphabetic letters (i.e., [a-z] and [A-Z]).

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day07/r-expressionsII.js)

## Day 7: Regular Expressions III

### Task
* Receive a string of s
* length of s ≥ 3
* s is a string that contains numbers and letters
* Write a regular expression that validates the string
* The expression must only output integer numbers

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/blob/master/day07/r-expressionsIII.js)

## Day 8: Create a Button 
### Task

Complete the code in the editor so that it creates a clickable button satisfying the following properties:

* The button's id is btn.
* The button's initial text label is . After each click, the button must increment by . Recall that the button's text label is the JS object's innerHTML property.
* The button has the following style properties:
* A width of 96px.
* A height of 48px.
* The font-size attribute is 24px.

The .js and .css files are in different directories, so use the link tag to provide the CSS file path and the script tag to provide the JS file path:

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="css/button.css" type="text/css">
    </head>
    
    <body>
    	<script src="js/button.js" type="text/javascript"></script>
    </body>
</html>
```
## Day 08 Buttons Container
### Task
Create nine buttons enclosed in a div, laid out so they form a **3 x 3** grid. Each button has a distinct label from**1 to 9**, and the labels on the outer buttons must rotate in the clockwise direction each time we click the middle button
   - Element IDs. Each element in the document mus have an id, 
       - The button container div/s **id** must be **btns**
       - The initial `ÌnnerText` labels must have  the different button Ids 
```js
innerHTML 1,2... id btn1, btn2...
```
*  . The documetnt's elements must  have the follwing style:
- The width is 30%, relativ to its container width
- The height is 48px.
- The font-size is 24p.
* Behavior . Each time btn5 is **clicked**, the `innerHTML` text on the grid's outer button(i.e, bt1, btn2, btn3,btn4,btn6, btn7, btn8,btn9) must roteate in the clockwise direction. Do not update the button id's.
* Include  **js and css** in the HTML file

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/tree/master/day08/button-container)

## Day 09 Binary Calculator
### Task
implement a simple cal that performs the following operations on binary nubmers:
`addition, subtraction, multiplication and division`
* divisionoperation must be **integer** division only; for example, 1001/100 = 10, 10,1110/101 = 10, and 101/1=101.
## Instructions
* Styling.
   - body has a width of 33 %
   - res has a background-color of lightgray, a border that is solid, a height of 48px, and a font-size of 20px.
   - btn0 and btn1 have a background-color of lightgreen and a color of brown.
   - btnClr and btnEql have a background-color of darkgreen and a color of white.
   - btnsum, btnSub, btnMul, and btnDiv have a background-color of black, a color of red
   - All the buttons in btns have a width of 25%, a height of 36px, a font-size of 18px, margin of 0px, and float value left.

[SOLUTIONS](https://github.com/chiarabdy/10DaysOfJavaScript-HackerRank/tree/master/day09)

##                      .. END ..