+++
title = "React Challenges"
date = "2019-09-05"
draft = false
pinned = false
image = "/img/react.png"
+++
## 1- Create a Simple JSX Element 

The current code uses **JSX** to assign a div element to the constant JSX. Replace the div with an h1 element and add the text Hello JSX! inside it. 

#### Instructions: 

   * add the text Hello JSX! inside it. 

[SULUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch000.jsx)

## 2- Create a Complex JSX Element

Define a new constant JSX that renders a div which contains the following elements in order:

An h1, a p, and an unordered list that contains three li items. You can include any text you want within each element.

Note: When rendering multiple elements like this, you can wrap them all in parentheses, but it's not strictly required. Also notice this challenge uses a div tag to wrap all the child elements within a single parent element. If you remove the div, the JSX will no longer transpile. Keep this in mind, since it will also apply when you return JSX elements in React components.
### Instructions:

   * The constant JSX should return a div element.
   * The div should contain a p tag as the second element.
   * The div should contain a ul tag as the third element.
   * The div should contain an h1 tag as the first element.
   * The ul should contain three li elements.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch001.jsx)

## 3- Add Comments in JSX

JSX is a syntax that gets compiled into valid JavaScript. Sometimes, for readability, you might need to add comments to your code. Like most programming languages, JSX has its own way to do this.

To put comments inside JSX, you use the syntax {/\* \*/}to wrap around the comment text.

The code editor has a JSX element similar to what you created in the last challenge. Add a comment somewhere within the provided divelement, without modifying the existing h1or pelements.

### Instructions:

   * The constant JSXshould return a divelement.
   * The divshould contain an h1tag as the first element.
   * The divshould contain a ptag as the second element.
   * The JSXshould include a comment.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch002.jsx)

## 4- Render HTML Elements to the DOM

So far, you've learned that JSX is a convenient tool to write readable HTML within JavaScript. With React, we can render this JSX directly to the HTML DOM using React's rendering API known as ReactDOM.

ReactDOM offers a simple method to render React elements to the DOM which looks like this: ReactDOM.render(componentToRender, targetNode), where the first argument is the React element or component that you want to render, and the second argument is the DOM node that you want to render the component to.

As you would expect, ReactDOM.render()must be called after the JSX element declarations, just like how you must declare variables before using them.


The code editor has a simple JSX component. Use the ReactDOM.render()method to render this component to the page. You can pass defined JSX elements directly in as the first argument and use document.getElementById()to select the DOM node to render them to. There is a divwith id='challenge-node'available for you to use. Make sure you don't change the JSXconstant.
### Instructions:

   * The constant JSXshould return a divelement.
   * The divshould contain an h1tag as the first element.
   * The divshould contain a ptag as the second element.
   * The provided JSX element should render to the DOM node with id challenge-node.

  [SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch003.jsx)

## 5- Define an HTML Class in JSX

Apply a class of myDivto the divprovided in the JSX code.
### Instructions:

   * The constant JSXshould return a divelement.
   * The divhas a class of myDiv.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch004.jsx)

## 6- Learn About Self-Closing JSX Tags

Fix the errors in the code editor so that it is valid JSX and successfully transpiles. Make sure you don't change any of the content - you only need to close tags where they are needed.
### Instructions:

   * The constant JSXshould return a divelement.
   * The divshould contain a brtag.
   * The divshould contain an hrtag.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch005.jsx)

## 7- Create a Stateless Functional Component

The code editor has a function called MyComponent. Complete this function so it returns a single divelement which contains some string of text.
Note: The text is considered a child of the divelement, so you will not be able to use a self-closing tag.
### Instructions:

   * MyComponentshould return JSX.
   * MyComponentshould return a divelement.
   * The divelement should contain a string of text.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch006.jsx)

## 8- Create a React Component

The other way to define a React component is with the ES6 classsyntax

MyComponentis defined in the code editor using class syntax. Finish writing the rendermethod so it returns a divelement that contains an h1with the text Hello React!.
### Instructions:

   * The React component should return a divelement.
   * The returned divshould render an h1header within it.
   * The h1header should contain the string Hello React!.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch007.jsx)

## 9- Create a Component with Composition
 we can compose multiple React components together. Imagine you are building an App and have created three components, a **Navbar**, **Dashboard**, and **Footer**. To compose these components together, you could create an **App** parent component which renders each of these three components as children. To render a component as a child in a React component, you include the component name written as a custom HTML tag in the JSX. For example, in the **render** method you could write:

### Instructions

   * The React component should return a single divelement.
   * The component should return two nested elements.
   * The component should return the ChildComponent as its second child  

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch008.jsx)

## 10- Use React to Render Nested Components

Component composition is one of React's powerful features. When you work with React, it is important to start thinking about your user interface in terms of components like the App example in the last challenge. You break down your UI into its basic building blocks, and those pieces become the components. This helps to separate the code responsible for the UI from the code responsible for handling your application logic. It can greatly simplify the development and maintenance of complex projects.

### Instructions
   * The TypesOfFoodcomponent should return a single divelement.
   * The TypesOfFoodcomponent should return the Fruitscomponent.
   * The Fruitscomponent should return the TypesOfFruitcomponent.
   * The TypesOfFruitcomponent should return the h2and ulelements.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch009.jsx)

## 11- Compose React Components

Rendering ES6 style class components within other components is no different than rendering the simple components you used in the last few challenges. You can render JSX elements, stateless functional components, and ES6 class components within other components.
### Instructions 
   * The TypesOfFood component should return a single div element.
   * The TypesOfFood component should return the Fruits component.
   * The Fruits component should return the NonCitrus component and the Citrus component.
   * The TypesOfFood component should return the Vegetables component below the Fruits component.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch010.jsx)

## 12- Render a Class Component to the DOM

The process for ***rendering*** ```React components``` is very similar to using the ***ReactDOM API***

Syntax:
```js
ReactDOM.render(componentToRender, targetNode)
//The first argument is the React component that you want to render. 
//The second argument is the DOM node that you want to render that component within.
```
React components are passed into ``ReactDOM.render()`` a little differently than **JSX** elements. ```For JSX elements```, you pass in the ***name of the element that you want to render***. However, ```for React components```, you need to use the same syntax as if you were rendering a nested component, for example 
```js 
ReactDOM.render(<ComponentToRender />, targetNode). 
```
You use this syntax for both ***ES6 class components*** and ***functional components***.

### Instructions
   * The TypesOfFood component should return a single div element.
   * The TypesOfFood component should render the Fruits component after the h1 element.
   * The TypesOfFood component should render the Vegetables component after Fruits.
   * The TypesOfFood component should render to the DOM within the div with the id challenge-node.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch011.jsx) 

## 13- Write a React Component from Scratch
a typical React component is an **ES6 class** which extends ``React.Component``. It has a ``render`` method that ``returns`` HTML (from JSX) or null.

#### Requires
Define a class **MyComponent** that ***extends*** **React.Component**. Its **render method** should **return** a ***div*** that contains an **h1** tag with the ***text***: ``My First React Component!`` in it. Use this text exactly, the case and punctuation matter. Make sure to call the **constructor** for your component, too.

**Render** this component to the **DOM** using ```ReactDOM.render()```. There is a div with ``id='challenge-node'`` available for you to use.

### Instructions
   * There should be a React component called MyComponent.
   * MyComponent should contain an h1 tag with text My First React Component! Case and punctuation matter.
   * MyComponent should render to the DOM.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch012.jsx) 

## 14- Pass Props to a Stateless Functional Component
In React, you can pass **props**, or properties, to child components.

#### Requires:
   When ***rendering*** **CurrentDate** from the **Calendar** component, pass in a property 
   of date assigned to the current date from JavaScript's ``Date`` object. 
   Then access this prop in the **CurrentDate** component, showing its value within the **p** tags.
   Note that for prop values to be evaluated as JavaScript, they must 
   be enclosed in curly brackets, for instance ``date={Date()}``.

### Instructions:
   * The Calendar component should return a single div element.
   * The second child of the Calendar component should be the CurrentDate component.
   * The CurrentDate component should have a prop called date.
   * The date prop of the CurrentDate should contain a string of text.
   * The date prop should be generated by calling Date()
   * The CurrentDate component should render the value from the date prop in the p tag.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch013.jsx)

## 15- User Default Props

### Instructions:
* The ShoppingCart component should render.
* The ShoppingCart component should have a default prop of { items: 0 }.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch014.jsx)

## 16- Override Default Props

### Instructions: 
* The component ShoppingCart should render.
* The component Items should render.
* The Items component should have a prop of { quantity: 10 } passed from the ShoppingCart component.

[SOLUTIONS](https://github.com/chiarabdy/lernblogTesting/blob/master/content/challenges/react/ch015.jsx)

## 17- Use PropTypes to Define the Props you Expect
### Typechecking with PropTypes
      React provides useful type-checking features to verify that components receive
      props of the correct type. For example, your application makes an API call 
      toretrieve data that you expect to be in an array, which is then passed to a 
      component as a prop. You can set propTypes on your component to require the data 
      to be of type array. This will throw a useful warning when the data is of any 
      other type.

```js
import React from 'react';
import PropTypes from 'prop-types';
 
class MyComponent extends React.Component {
  render() {
    // ... do things with the props
  }
}
 
MyComponent.propTypes = {
  // You can declare that a prop is a specific JS primitive. By default, these
  // are all optional.
  optionalArray: PropTypes.array,
  optionalBool: PropTypes.bool,
  optionalFunc: PropTypes.func,
  optionalNumber: PropTypes.number,
  optionalObject: PropTypes.object,
  optionalString: PropTypes.string,
  optionalSymbol: PropTypes.symbol,
 
  // Anything that can be rendered: numbers, strings, elements or an array
  // (or fragment) containing these types.
  optionalNode: PropTypes.node,
 
  // A React element (ie. <MyComponent />).
  optionalElement: PropTypes.element,
 
  // A React element type (ie. MyComponent).
  optionalElementType: PropTypes.elementType,
 
  // You can also declare that a prop is an instance of a class. This uses
  // JS's instanceof operator.
  optionalMessage: PropTypes.instanceOf(Message),
```
      Define propTypes for the Items component to require quantity as a 
      prop and verify that it is of type number.

## Instructions
* The ShoppingCart component should render.
* The Items component should render.
* The Items component should include a propTypes check that requires quantity to be a number.

[SOLUTIONS](https://github.com/chiarabdy/freecodecamp-react/blob/master/react%2017.jsx)

