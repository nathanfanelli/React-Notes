React.js is a javascript library. 

Why React?

- React is FAST. Apps made with React can handle complex updates and still feel quick and responsive. 
- React is MODULAR. Instead of writing large, dense files of code, you can write smaller, reusable ones. 
- React is SCALABLE. Large programs that display a lot of changing data are where React performs best. 
- React is FLEXIBLE. You can use React for interesting projects that have nothing to do with making web applications. 
- React is POPULAR. React can make you employable. 

When using React, we tend to use JSX to create HTML elements as opposed to using DOM methods in Vanilla JavaScript. 

JSX is stored in JS files. 
JSX is a syntax extension for JS. It was written to be used with JS. JSX code looks a lot like HTML. 
By “syntax extension”, we mean that JSX is not valid JS. Web browsers can’t read it! If a JS file contains JSX code, the file will need to be compiled. Meaning that before the file reaches a web browser, a JSX compiler will translate any JSX into regular JS. Browsers don’t have their own JSX compiler, so we need to run a compiler locally. 

JSX Elements

A basic unit of JSX is called  a JSX element. 

Ex: <h1>Hello World</h1>

This JSX element looks exactly like HTML. The only noticeable difference is that you would find this in a JS file as opposed to an HTML file. JSX elements are merely descriptions of what we want to see on our page. 

JSX Elements and their surroundings

JSX elements are treated as JS expressions. They can go anywhere that JS expressions can go. That means that a JSX element can be saved in a variable, passed to a function, stored in an object or array and more. 

Ex. of JSX element stored in a variable: const navBAr = <nav>I am a nav bar</nav>;

Ex. of several JSX elements being stored in an object: 
const myTeam = {
  center: <li>Benzo Walli</li>,
  powerForward: <li>Rasha Loa</li>,
  smallForward: <li>Tayshaun Dasmoto</li>,
  shootingGuard: <li>Colmar Cumberbatch</li>,
  pointGuard: <li>Femi Billon</li>
};

Attributes in JSX

JSX elements have attributes just like HTML elements. A JSX attribute is written using HTML-like syntax: a name, followed by an equal sign, followed by a value. The value should be wrapped in quotes, like this: 

my-attribute-name=“my-attribute-value”

Here are some JSX elements with attributes: 

<a href=“#”>Welcome to the web</a>;

const title = <h1 id=“title”>Introduction to React.js: Part 1</h1>;

A single JSX element can have multiple attributes, like so: 

const panda = <img src=“” alt=“” width=“#” height=“”

Nested JSX

You can nest JSX elements inside of other JSX elements, just like in HTML. Here’s an example of a JSX <h1> element, nested inside of a JSX <a> element: 

<a href=“#”><h1>Click me!</h1></a>

If a JSX expression takes up more than one line, then you must wrap the multi-line JSX expression in parentheses. This looks strange at first, but you get used to it: 

Ex: 

(
  <a href="https://www.example.com">
    <h1>
      Click me!
    </h1>
  </a>
)

Nested JSX expressions can be saved as variables, passed to function, etc., just like non-nested JSX expressions can! Here’s an example of a nested JSX expression being saved as a variable: 

 const theExample = (
   <a href="https://www.example.com">
     <h1>
       Click me!
     </h1>
   </a>
 );

JSX Outer Elements 

JSX Expressions must have exactly one outermost element. 

The first opening tag and the final closing tag of a JSX expression must belong to the same JSX element. If you notice that a JSX expression has multiple outer elements, the solution is usually simple: wrap the JSX expression in a <div></div>.

Outer most JSX lines can be semantic tags other than <div> tags as long as they adhere to nesting permissions in HTML. 

To render JSX elements to the page, use: ReactDOM.render();

Ex: 

ReactDOM.render(<h1>Hello world</h1>, document.getElementById('app'));

React is the JS library for building interfaces and ReactDOM is the JS library that allows React to interact with the DOM. ReactDOM is a library of many methods. 

ReactDOM.render()’s first argument should be a JSX expression, and it will be rendered to the screen. ReactDOM is NOT included in the generic React library. We will have to incorporate an additional script tag in our HTML for the ReactDOM library if that is something we want to use. 

Virtual DOM

ReactDOM.render() only updates DOM elements that have changed. If you render the exact same thing twice in a row, the second render will do nothing. 

In React, for every DOM object, there is a corresponding “virtual DOM object”. A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing’s power to directly change what’s on the screen. 

Manipulating the real DOM is slow, while changing the virtual DOM is much faster because nothing gets drawn onscreen. Think of manipulating the virtual DOM as making changes to blueprint, as opposed to moving rooms in an actual house. 
