ADVANCED JSX

Grammar in JSX is mostly the same as it is in HTML, but there are a few subtle difference to be on the lookout for. The most common is the use of the word ‘class’.

In HTML, it’s  common to use ‘class’ as an attribute name: <h1 class=“#”>Hey</h1>

In JSX, you can’t use ‘class’! You have to use ‘className’ instead: 
<h1 className=“#”>Hey</h1>

This is because JSX gets translated into JavaScript, and ‘class’ is a reversed word in JS. When JSX is rendered, JSX ‘className’ attributes are automatically rendered as ‘class’ attributes. 

The two main attributes that are reversed keywords in JS you can’t use in JSX are: 
1. class - is ‘className’ in JSX
2. for - is ‘htmlFor’ in JSX

In JSX, self-closing tags are different. 

Ex: 

Fine in JSX:

  <br />

NOT FINE AT ALL in JSX:

  <br>

In JSX, HTML elements can be self-closing as long as we use the forward slash syntax. However, we should only create self-closing syntax when an element has no children. That is the only time we should use self-closing syntax on elements that are normally not self-closing. 

When we inject JS into JSX we can make this process of rendering logic (based on things like data, events, and data changing over time) more seamless by putting our markup, the HTML part of JSX, that is based on our logic, the JS part of JSX, together in the same file.

Any code in between the tags of a JSX element will be read as JSX, not as regular JS. JSX doesn’t add numbers - it reads them as text, just like HTML. 

To write JS inside of JSX, you are going to write all JS in curly braces. 

Ex: 

import React from 'react';
import ReactDOM from 'react-dom';

let myVar = 'hello!';

const myJsxElement = <h1>myVar value is {myVar}</h1>; // `myVar` without curly braces will render as `myVar` in the browser, while `{myVar}` will render as `hello!` in the browser 

ReactDOM.render(
        myJsxElement,
        document.getElementById('app')
);

The curly braces themselves won’t be treated as JSX nor JS. They are simply markers used to indicate the beginning and the end of a JS injection into JSX. 

When you inject JS into JSX, that JS is part of the same environment as the rest of JS in your file. This means that you can access variables inside of a JSX expression, even if those variables are declared on the outside. 

Ex: 
// Declare a variable:
const name = ‘Gerdo’;

// Access your variable 
// from inside of a JSX expression: 
const greeting = <p>Hello, {name}!</p>;

We usually will want to variables assigned to our JS expressions when our JS code would otherwise be hard to read/follow before using our JS expression inside of our JSX. 

When writing JSX, it’s common to use variables to set attributes. 

Ex: 

// Use a variable to set the `height` and `width` attributes:

const sideLength = "200px";

const panda = (
  <img 
    src="images/panda.jpg" 
    alt="panda" 
    height={sideLength} 
    width={sideLength} />
);

Note that the <img> tag’s attributes get their own line. This makes the code more readable. Object properties are also often used to set attributes: 

const pics = {
  panda: "http://bit.ly/1Tqltv5",
  owl: "http://bit.ly/1XGtkM3",
  owlCat: "http://bit.ly/1Upbczi"
}; 

const panda = (
  <img 
    src={pics.panda} 
    alt="Lazy Panda" />
);

const owl = (
  <img 
    src={pics.owl} 
    alt="Unimpressed Owl" />
);

const owlCat = (
  <img 
    src={pics.owlCat} 
    alt="Ghastly Abomination" />
); 

JSX elements can have event listeners, just like HTML elements can. Programming in React means constantly working with event listeners. You create an event listener by giving a JSX element a special attribute. 
Ex: 

<img onClick={myFunc} />

An event listener’s attribute name should be something like onClick or onMouseOver: the word ‘on’, plus the type of event that you’re listening for. An event listener’s attribute name should be a function. The above example would only work if myFunc were a valid function that had been defined elsewhere: 

function myFunc() {
  alert('Make myFunc the pFunc... omg that was horrible i am so sorry');
}

<img onClick={myFunc} />

Note that in HTML, event listener names are written in all lowercase, such as onclick or onmouseover. In JSX, they are written in camelCase. 

If we set the event listener attribute value to a function call, the function will automatically get called on the page load (when our JSX element renders to the browser) instead of listening for the event and THEN calling the function


JSX Cond	itionals

You CANNOT inject ‘if’ statements into JSX. They will break your code. This is because of the way JSX is compiled. 

One way to write a conditional in JSX is to write an ‘if’ statement, and no inject it into JSX. You can write if/else statements in JSX as long as the keywords ‘if’ and ‘else’ remain OUTSIDE of JSX tags. 

You can hide and show elements conditionally if you pass in the null property in an ‘if’ statement. 

The ternary operator works the same way in JSX as in JS and is found in React code quite frequently. 

Ex. of ternary operator in JSX: 

const headline = (
  <h1>
    { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
  </h1>
);

Like the ternary operator the ‘&&’ operator shows up frequently. 

If you want to create a list of JSX elements, then .map() is often your best bet. 
Ex: 

const strings = ['Home', 'Shop', 'About Me'];

const listItems = strings.map(string => <li>{string}</li>);

<ul>{listItems}</ul>


// This is fine in JSX, not in an explicit array:

<ul>
  <li>item 1</li>
  <li>item 2</li>
  <li>item 3</li>
</ul>

// This is also fine!

const liArray = [
  <li>item 1</li>, 
  <li>item 2<li>, 
  <li>item 3</li>
];

<ul>{liArray}</ul>

When you make a list in JSX, sometimes your list will need to include something called keys:

<ul>
  <li key="li-01">Example1</li>
  <li key="li-02">Example2</li>
  <li key="li-03">Example3</li>
</ul>

A key is a JSX attribute. The attribute’s name is key. The attribute’s value should be something unique, similar to an id attribute.
keys don’t do anything that you can see! React uses them internally to keep track of lists. If you don’t use keys when you’re supposed to, React might accidentally scramble your list-items into the wrong order.

You can write React code without JSX at all!

The majority of React programmers do use JSX, but you should understand you do not need it. 

Ex: 

const h1 = <h1>Hello world</h1>; 

can be rewritten as: 

const h1 = 
	React.createElement(
		“h1”,
		null, 
		“hello, world”
);

When a JSX element is compiled, the compiler transforms the JSX element into the method that you see above: React.createElement(). Every JSX element is secretly a call to React.createElement().

We would use React.createElement() instead of JSX when we do not want to set up compilation for our project, which the use of JSX requires!

