THIS.PROPS

Every component has something called ‘props’. 

A component’s props is an object. It holds informations about that component. 

To see a component’s props object, you use the expression: ‘this.props’. Example of this.props being used in a render method: 

render() {
  console.log("Props object comin' up!");

  console.log(this.props);

  console.log("That was my props object!");

  return <h1>Hello world</h1>;
}

most of the information in this.props is pretty useless. But some of it is extremely important as you’ll see.

you can pass information to a React component. How? by giving that component an attribute: 

<MyComponent foo=“bar” />

Let’s say you want to pass a component the message “This is some top secret info.” Here’s how you do it: 

<Example message=“This is some top secret info.” />

As you see, to pass information to a component, you need a name for the information you want to pass. In the above example, we used the name ‘message’. You can use any name you want. If you want to pass information to a string, then wrap that information in curly braces. Here’s how you would pass an array: 

<Greeting myInfo={["top", "secret", "lol"]} />

In this next example, we pass every pieces of information to <Greeting />. The values that aren’t strings are wrapped in curly braces: 

<Greeting name="Frarthur" town="Flundon" age={2} haunted={false} />

You will often want to make a component display passed-in information. 

1. Find the component class that is going to receive that information. 
2. Include this.props.name-of-information in that component class’s render method’s return statement. 

We have now learned how to pass a prop to a component. 

<Greeting firstName=“Bruce” />

We have also learned how to access and display a passed-in prop: 

render() {
  return <h1>{this.props.firstName}</h1>;
}

The most common use of ‘props’ is to pass information to a component, from a different component. 

props is the name of the object that stores passed-in information. this.props refers to that storage object. At the same time, each piece of passed-in information is called a prop. This means that props could refer to two pieces of passed-in information, or it could refer to the object that stores those pieces of information. 

You can do more with props than just display them. You can also use props to make decisions. 

You can, and often will pass functions as props. It is especially common to pass event handler functions. 

To define an event handler in React, you define an event handler as a method on the component class, just like the render method. Almost all functions you define in React, will be define this way, as methods in a class. 

Great! You just passed a function from <Talker /> to <Button />.
In the code editor, select Button.js. Notice that Button renders a <button></button> element.
If a user clicks on this <button></button> element, then you want your passed-in talk function to get called.
That means that you need to attach talk to the <button></button> as an event handler.
How do you do that? The same way that you attach any event handler to a JSX element: you give that JSX element a special attribute. The attribute’s name should be something like onClick or onHover. The attribute’s value should be the event handler that you want to attach.

Let’s talk about naming things.
When you pass an event handler as a prop, as you just did, there are two names that you have to choose.
Both naming choices occur in the parent component class - that is, in the component class that defines the event handler and passes it.
The first name that you have to choose is the name of the event handler itself.
Look at Talker.js, lines 6 through 12. This is our event handler. We chose to name it talk.
The second name that you have to choose is the name of the prop that you will use to pass the event handler. This is the same thing as your attribute name.
For our prop name, we also chose talk, as shown on line 15:
return <Button talk={this.talk} />;
These two names can be whatever you want. However, there is a naming convention that they often follow. You don’t have to follow this convention, but you should understand it when you see it.
Here’s how the naming convention works: first, think about what type of event you are listening for. In our example, the event type was “click.”
If you are listening for a “click” event, then you name your event handler handleClick. If you are listening for a “keyPress” event, then you name your event handler handleKeyPress:

class MyClass extends React.Component {
  handleHover() {
    alert('I am an event handler.');
    alert('I will be called in response to "hover" events.');
  }
}
Your prop name should be the word on, plus your event type. If you are listening for a “click” event, then you name your prop onClick. If you are listening for a “keyPress” event, then you name your prop onKeyPress:
class MyClass extends React.Component {
  handleHover() {
    alert('I am an event handler.');
    alert('I will listen for a "hover" event.');
  }

  render() {
    return <Child onHover={this.handleHover} />;
  }
}

Every components props object has a property named children. 

this.props.children will return everything in between a component’s opening and closing JSX tags. 

If a component has more than one child between its JSX tags, then this.props.children will return those children in an array. However, if a component has only one child, then this.props.children will return the single child, not wrapped in an array.

defaultProps should be equal to an object: 

class Example extends React.Component {
  render() {
    return <h1>{this.props.text}</h1>;
  }
}

// Set defaultProps equal to an object:
Example.defaultProps = {};

Inside of this object, write properties for any default props that you’d like to set:

class Example extends React.Component {
  render() {
    return <h1>{this.props.text}</h1>;
  }
}

Example.defaultProps = { text: 'yo' }; 


