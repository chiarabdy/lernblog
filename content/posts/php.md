+++
title = "PHP"
date = "2020-09-24"
draft = false
pinned = false
image = "/img/php.jpg"
+++
**PHP** is a server scripting language, and a powerful tool for making dynamic and interactive Web pages.

## SYNTAX
```php
<?php
// PHP code goes here
?>
```
## Data Type

### String
1. `strlen()` to get the string length
2. `strrev()` to reverse the string
3. `str_replace('old','new','var')`
```php
$oldtxt = "Hello World!";
$newtxt = str_replace("World", "Dolly", $oldtxt)
```
### Variables
In PHP, a variable starts with the `$` sign, followed by the name of the variable:
```php
<?php
$txt = "Hello world!";
$x = 1;
$y = 10.5;
?>
```
### PHP Variables Scope
In PHP, variables can be declared anywhere in the script.

The scope of a variable is the part of the script where the variable can be referenced/used.

PHP has `three different variable scopes`:
* Local
* Global
* Static
### Global and Local Scope
A `variable` declared outside a function has a GLOBAL SCOPE and can only be accessed outside a function:
```php
<?php
$x = 5; // global scope

function myTest() {
  // using x inside this function will generate an error
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

echo "<p>Variable x outside function is: $x</p>";
?>
```
A `variable` declared within a function has a **LOCAL** SCOPE and can only be accessed within that function:
```php
<?php
function myTest() {
  $x = 5; // local scope
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

// using x outside the function will generate an error
echo "<p>Variable x outside function is: $x</p>";
?>
```
### PHP The global Keyword
The global keyword is used to access a global variable from within a function.
To do this, use the global keyword before the variables (inside the function):
```php
<?php
$x = 5;
$y = 10;

function myTest() {
  global $x, $y;
  $y = $x + $y;
}

myTest();
echo $y; // outputs 15
?>
```
### PHP The static Keyword
Normally, when a function is completed/executed, all of its variables are deleted. However, sometimes we want a local variable NOT to be deleted. We need it for a further job.

To do this, use the static keyword when you first declare the variable
```php
<?php
function myTest() {
  static $x = 0;
  echo $x;
  $x++;
}

myTest();
myTest();
myTest();
?>
```
### echo and print
`echo` and `print` are more or less the same. They are both used to output data to the screen. 
The only differences are that `echo` has no return value while `print` has a return value of 1 so it can be used in expressions. `echo` can take multiple parameters (although such usage is rare) while `print` can take one argument. `echo` is marginally faster than print.

The ***echo*** statement can be used with or without **parentheses**: `echo` or `echo()`.

## Arrays
An array is a special variable, which can hold more than one value at a time.

### Create an Array in PHP
1. by using the function `array();`

```php
<?php
$cars = array("Volvo", "BMW", "Toyota");
print_r ($cars);
echo '</br>';
var_dump($cars);
echo '</br>';
echo count($cars)
?>
```
### Keys and Values
```php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
echo "Ben is " . $age["Ben"] . " years old.";
```
2. Indexed Arrays

```php
$cars = ["Volvo", "BMW", "Toyota"]
echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";
```

## Loop Throgh an Inedexed Array
1. `for` Loop
To loop through and print all the values of an indexed array, you could use a for loop, like this:
```php
<?php
$cars = array("Volvo", "BMW", "Toyota");
$arrlength = count($cars);

for($i = 0; $i < $arrlength; $i++) {
  echo $cars[$i];
  echo "<br>";
}
?>
```
2. `foreach` Loop
### SYNTAX
```php
foreach ($array as $value) {
  code to be executed;
}
```
### Example
```php
<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach($age as $x => $val) {
  echo "$x = $val<br>";
}
?>
```

`var_dump()`: Dumps information about a variable.

This function displays structured information about one or more expressions that includes its type and value. Arrays and objects are explored recursively with values indented to show structure.

```php
<?php
$cars = array("Volvo","BMW","Toyota");
var_dump($cars);
?>
```
