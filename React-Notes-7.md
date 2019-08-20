THIS.STATE

Dynamic information is information that can change. 

React components will often need dynamic information in order to render. For example, imagine a component that displays the score of a basketball game. The score of the game might change over time, meaning that the score is dynamic. Our component will have to know the score, a piece of dynamic information, in order to render in a useful way.

There are two ways for a component to get dynamic information: props and state. Besides props and state, every value used in a component should always stay exactly the same.

A React component can access dynamic information in two ways: props and state. 

Unlike props, a component’s state is not passed in from outside. A component decides its own state. 

To make a component have state, give the component a state property. This property should be declared inside of a constructor method. Like this: 

class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = { mood: 'decent' };
  }

  render() {
    return <div></div>;
  }
}

<Example />

It is important to note that React components always have to call super in their constructors to be set up properly.

To read a component’s state, use the expression: this.state.name-of-property: 

class TodayImFeeling extends React.Component {
  constructor(props) {
    super(props);
    this.state = { mood: 'decent' };
  }

  render() {
    return (
      <h1>
        I'm feeling {this.state.mood}!
      </h1>
    );
  }
}

Just like this.props, you can use this.state from any property defined inside of a component class’s body.

A component can do more than just read its own state. A component can also change its own state. 

A component changes its state by calling the function this.setState().

this.setState() takes two arguments: an object that will update the component’s state, and a callback. You basically never need the callback.

this.setState() takes an object and merges that object with the component’s current state. If there are properties in the current state that aren’t part of that object, then those properties remain how they were. 

The most common way to call this.setState() is to call a custom function that wraps a this.setState() call. .makeSomeFog() is an example: 

class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = { weather: 'sunny' };
    this.makeSomeFog = this.makeSomeFog.bind(this);
  }

  makeSomeFog() {
    this.setState({
      weather: 'foggy'
    });
  }
}

Notice how the method makeSomeFog() contains a call to this.setState(). 

You may have noticed a strange line in there: 

this.makeSomeFog = this.makeSomeFog.bind(this);

This line is necessary because makeSomeFog()’s body contains the word this. 

Here is how <Mood />’s state would be set: 

1. A user triggers an event (in this case a click event triggered by clicking on a <button>).
2. The event from step 1 is being listed for (in this case by the onClick attribute on line 20. 
3. When this listened-for event occurs, it calls an event handler function (in this case, this.toggleMood(), called on line 20 and define on lines 11-14).
4. Inside of the body of the event handler, this.setState() is called(line 13).
5. The component’s state is changed.

Due to the way that event handler’s are bound in JavaScript, this.toggleMood() loses its this when it is used on line 20. Therefore, the expressions this.state.mood and this.setState on lines 7 and 8 won’t mean what they’re supposes to… unless you have already bound the correct this.toggleMood. 

That is why we must bind this.toggleMood to this on line 8. 

Just know that in React, whenever you define an event handler that uses this, you need to add this.methodName = this.methodName.bind(this) to your constructor function.

One final note: you can’t call this.setState() from inside of the render function!

Here’s why: Any time that you call this.setState(), this.setState() AUTOMATICALLY calls .render() as soon as the state has changed.

Think of this.setState() as actually being two things: this.setState(), immediately followed by .render().

That is why you can’t call this.setState() from inside of the .render() method! this.setState() automatically calls .render(). If .render() calls this.setState(), then an infinite loop is created.

A React app is basically just a lot of components, setting state and passing props to one another. Now that you have a real understanding of how to use props and state, you have by far the most important tools that you need!
