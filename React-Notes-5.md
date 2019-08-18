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




COMPONENTS RENDER OTHER COMPONENTS

A React application can contain dozens, or even hundreds of components. 

Each component may be small on its own, however, when combined with other smaller components, they can create a massive ecosystem of information. 

What makes React special is the ways in which components interact, not components themselves. 

We know render methods can return HTML-like JSX elements. Render methods can also return components, or ‘component instances’: 

class OMG extends React.Component {
  render() {
    return <h1>Whooaa!</h1>;
  }
}

class Crazy extends React.Component {
  render() {
    return <OMG />;
  }
}

In the above example, Crazy’s render method returns an ‘instance’ of the OMG component class. You could say that ‘Crazy’ renders an <OMG />

When a component renders another component, what happens is very similar to what happens when ReactDOM.render() renders a component. 

To make a class component render another class component, simply type the class component’s name into the render method. Ex: <NavBar />

When you use React.js, every JS file in your application is invisible to every other JS file by default. 

To import a variable from another JS file, you will use an ‘import statement’: 

import { NavBar } from './NavBar.js';

If you use an import statement and the string at the end begins with either a dot of a slash, then import all treat that string as a file path. import will follow that file path and import the file that it finds. 

If your file path doesn’t have a file extension, then ‘.js’ is assumed. 

None of this behavior is specific to React. Module systems of independent, important files are a very popular way to organize code. 

When you import a variable from a file that is not the current file, then an import statement is not enough. You will also need an export statement, written in the OTHER file, exporting the variable you wish to extract. 

import and export are intended to be used together and seldom will you see one used without the other. 

One way to export is to use something called ‘named exports’. Here’s how: 

In one file, place the keyword export immediately before something that you want to export. That something can be any top-level var, let, const, function, or class: 

// Manifestos.js:

export const faveManifestos = {
  futurist: 'http://www.artype.de/Sammlung/pdf/russolo_noise.pdf',
  agile: 'https://agilemanifesto.org/iso/en/manifesto.html',
  cyborg:   'http://faculty.georgetown.edu/irvinem/theory/Haraway-CyborgManifesto-1.pdf'
};

You can also export multiple items from the same file: 

// Manifestos.js:

export const faveManifestos = {
  futurist: 'http://www.artype.de/Sammlung/pdf/russolo_noise.pdf',
  agile:  'https://agilemanifesto.org/iso/en/manifesto.html',
  cyborg:   'http://faculty.georgetown.edu/irvinem/theory/Haraway-CyborgManifesto-1.pdf'
};

export const alsoRan = 'TimeCube';

In a different file, import the name of the var, let, const, function, or class from the first file:

// App.js:

// Import faveManifestos and alsoRan from ./Manifestos.js:
import { faveManifestos, alsoRan } from './Manifestos';

// Use faveManifestos:
console.log(`A Cyborg Manifesto:  ${faveManifestos.cyborg}`); 

This style of importing and exporting in JavaScript is known as “named exports.” When you use named exports, you always need to wrap your imported names in curly braces, such as:

import { faveManifestos, alsoRan } from './Manifestos';`
