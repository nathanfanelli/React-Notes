COMPONENTS AND ADVANCED JSX

A multi-line JSX expression should ALWAYS be wrapped in parentheses. That’s why multiple lines after a return statement are wrapped in parentheses. 

You can and often will inject JS into JSX inside of a render function. 

Using variables to set a component’s attributes is a nice way of improving organization and readability of your code. 

A render() function must have a return statement. However, that isn’t all it can have. 

A render() function can also be a fine place to put simple calculations that need to happen right before a component renders. Here’s an example of some calculations that need to take place before the component renders: 

class Random extends React.Component {
  render() {
    // First, some logic that must happen
    // before rendering:
    const n = Math.floor(Math.random() * 10 + 1);
    // Next, a return statement
    // using that logic:
    return <h1>The number is {n}!</h1>;
  }
}

You can place an ‘if’ statement inside of a render function if you place it before the return statement. Like so: 

class TodaysPlan extends React.Component {
  render() {
    let task;
    if (!apocalypse) {
      task = 'learn React.js'
    } else {
      task = 'run around'
    }

    return <h1>Today I am going to {task}!</h1>;
  }
}

The word ‘this’ gets used in React a lot. You are especially likely to see ‘this’ inside of a body of a component class declaration. Here’s an example: 

class IceCreamGuy extends React.Component {
  get food() {
    return 'ice cream';
  }

  render() {
    return <h1>I like {this.food}.</h1>;
  }
}

In this particular example, the keyword ‘this’ refers to an instance of the  IceCreamGuy component. Getter methods don’t need parentheses. 

Render functions often contain event listeners. Ex: 

render() {
  return (
    <div onHover={myFunc}>
    </div>
  );
}

Recall that an event handler is a function that gets called in response to an event. In the above example, myFunc is the event handler. 

In React, you define event handlers as methods on a component class. Ex: 

class MyClass extends React.Component {
  myFunc() {
    alert('Stop it.  Stop hovering.');
  }

  render() {
    return (
      <div onHover={this.myFunc}>
      </div>
    );
  }
}

Here, the component class has two methods: render() and myFunc(). myFunc() is being used as the event listener. 
