YOUR FIRST REACT COMPONENT

React applications are made out of components. 

A component is a small, reusable chunk of code that is responsible for one job. That job is often to render some HTML. 

import React from ‘react’; // this line creates a new variable. That variable’s name is React, and it’s value is a particular, imported JS object: This imported object contains methods that you need win order to use React. The object  is called the React library. 

Line 1 and 2 both import JS objects. In both lines, the imported object contains React-related methods. 

To clarify: the DOM is used in React applications, but it isn’t part of React. After all, the DOM is also used in countless non-React applications. Methods imported from ‘react’ are only for pure React purposes, such as creating components or writing JSX elements. 

You’ve learned that a React component is a small, reusable chunk of code that is responsible for one job, which often involves rendering HTML. 

Every component in React must come form a component class. A component class is like a factory that creates React components. If you have a component class, then you can that class to produce as many components as you want. To make a component class, you use a base class form the React library: React.Component.

React.component is a JavaScript class. To create your own component class, you must use subclass React.Component. To create your own component class, you must subclass React.Component. You can do this by using the syntax: 
	class YourComponentNameGoesHere extends React.Component{}.

JS classes and subclassing are complex topic beyond the scope of this course. 

To declare a new component class in  JSX, you must use subclassing. 

When you declare a new component class, you need to give that component class a name. Component class names begin with capital letters. This adheres to JS’s class syntax. it also adheres to a broader programming convention in which class names are written in UpperCamelCase. 

In addition, there is a React-specific reason why component class names must always be capitalized. 

Whenever you create a component class, you need to give that component class a name. That name should be written in UpperCamelCase. Ex: MyComponentClass

Like a JS classes, JSX classes need curly braces for the function body. The body will act as a set of instructions. Explaining to your component class how it should build a React component. 

Here’s what your class body should look like on its own, without the rest of the class declaration syntax: 

{
  render() {
    return <h1>Hello world</h1>;
  }
}

This doesn’t look like a set of instructions telling React to how to create a component, but it is. 

For starter’s, the instructions used to build React components should take the form of a class declaration body. That means  that they will be delimited by curly braces, like this: 

class ComponentFactory extends React.Component {
    // instructions go here, between the curly braces
}

A render method is a property whose name is render. and whose value is a function. The term render method can refer to the entire property, or to just the function part. 

A render method must contain a return statement. Usually, this return statement returns a JSX expression: 

class ComponentFactory extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}

Of course, none of this explains the point of a render method. All you know so far is that its name is render, it needs a return statement for some reason, and you have to include it in the body of your component class declaration. We’ll get to the ‘why’ of it soon. 
