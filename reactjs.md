# React JS

## **JSX**

It is a javascript code but it can using html tag

```
const h1 = <h1>Hey</h1>;
```

### class to className in JSX

```
const h1 = <h1 className="big">Hey</h1>;
```

### seft closing tag

```
Fine in JSX:

  <br />

NOT FINE AT ALL in JSX:

  <br>
```

### Curly Braces in JSX

```
import React from 'react';
import ReactDOM from 'react-dom';

// Write code here:
ReactDOM.render(
  <h1>{2 + 3}</h1>,
  document.getElementById('app')
);
```

### Variables in JSX

```
// Declare a variable:
const name = 'Gerdo';

// Access your variable
// from inside of a JSX expression:
const greeting = <p>Hello, {name}!</p>;
```

Object properties are also often used to set attributes:

```
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
```

### Event Listeners in JSX

JSX elements can have event listeners, just like HTML elements can. Programming in React means constantly working with event listeners.

```
<img onClick={myFunc} />
```

You can see a list of valid event names [here](http://facebook.github.io/react/docs/events.html#supported-events)

### JSX Conditionals: If Statements That Do Work

```
if (user.age >= drinkingAge) {
  message = (
    <h1>
      Hey, check out this alcoholic beverage!
    </h1>
  );
} else {
  message = (
    <h1>
      Hey, check out these earrings I got at Claire's!
    </h1>
  );
}

ReactDOM.render(
  message,
  document.getElementById('app')
);
```

### JSX Conditionals: The Ternary Operator

Every people that using React JS often use ternaty operator

```
const headline = (
  <h1>
    { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
  </h1>
);
```

-------- or ---------

```
const favoriteFoods = (
  <div>
    <h1>My Favorite Foods</h1>
    <ul>
      <li>Sushi Burrito</li>
      <li>Rhubarb Pie</li>
      {!judgmental && <li>Nacho Cheez Straight Out The Jar</li>}
      <li>Broiled Grapefruit</li>
    </ul>
  </div>
);
```

### .map in JSX or Array.map()

```
const strings = ['Home', 'Shop', 'About Me'];

const listItems = strings.map(string => <li>{string}</li>);

<ul>{listItems}</ul>
```

It like React try to destruct an array to inject string to HTML tag
here an example

```
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
```

### Keys

When you make a list in JSX, sometimes your list will need to include something called keys(Array_name + index):

```
<ul>
  <li key="li-01">Example1</li>
  <li key="li-02">Example2</li>
  <li key="li-03">Example3</li>
</ul>
```

React want developer to keep tracking item-list. If you don’t use keys when you’re supposed to, React might accidentally scramble your list-items into the wrong order.

```
const people = ['Rowe', 'Prevost', 'Gare'];

const peopleLis = people.map((person, i)=>{
  // expression goes here:
  <li key={'person_'+i}>{person}</li>
});

// ReactDOM.render goes here:
ReactDOM.render(<ul>{peopleLis}</ul>, document.getElementById('app'))
```

---

## **Component**

### Import React and render

Don't forget to import module when you use it

```
import React from 'react';
import ReactDOM from 'react-dom';


ReactDOM.render(
  <RactTag />,
  document.getElementById('app')
);

```

### Use a Variable Attribute in a Component

you should use data as an object

```
const redPanda = {
  src: 'https://upload.wikimedia.org/wikipedia/commons/b/b2/Endangered_Red_Panda.jpg',
  alt: 'Red Panda',
  width:  '200px'
};

class RedPanda extends React.Component {

  render() {
    return (
      <div>
        <h1>Cute Red Panda</h1>
        <img
          src={redPanda.src}
          alt={redPanda.alt}
          width={redPanda.width} />
      </div>
    );
  }
}

ReactDOM.render(
  <RedPanda />,
  document.getElementById('app')
);

```

**Note** : The curly blance in render() when you using value from obj type obj.key

### Put Logic in a Render Function

often see in Func render()

```
const friends = [
  {
    title: "Yummmmmmm",
    src: "https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-monkeyweirdo.jpg"
  }
];

// Logic component class starts here:
class Component extends React.Component {
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

ReactDOM.render(<Component />, document.getElementById('app'));
```

#### Don't!!!! do this

```
class Random extends React.Component {
  // This should be in the render function:
  const n = Math.floor(Math.random() * 10 + 1);

  render() {
    //----here you should put that logic---->
    return <h1>The number is {n}!</h1>;
  }
};
```

### Use this in a Component

The word this gets used in React a lot!

You are especially likely to see this inside of the **body** of a component class declaration. Here’s an example:

```
class IceCreamGuy extends React.Component {
  get food() {
    return 'ice cream';
  }

  render() {
    return <h1>I like {this.food}.</h1>;
  }
}
```

### Use an Event Listener in a Component

Render functions often contain event listeners. Here’s an example of an event listener in a render function:

```
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
```

**Note** : myFunc in curly blance at HTML tag no need ()

### Export & Import

In one file, place the keyword export immediately before something that you want to export. That something can be any top-level var, let, const, function, or class:

```
export const faveManifestos = {
  futurist: 'http://www.artype.de/Sammlung/pdf/russolo_noise.pdf',
  agile:  'https://agilemanifesto.org/iso/en/manifesto.html',
  cyborg:   'http://faculty.georgetown.edu/irvinem/theory/Haraway-CyborgManifesto-1.pdf'
};

export const alsoRan = 'TimeCube';
```

**Note** : You can export multiple things from the same file.

In a different file, import the name of the var, let, const, function, or class from the first file:

```
// App.js:

// Import faveManifestos and alsoRan from ./Manifestos.js:
import { faveManifestos, alsoRan } from './Manifestos';

// Use faveManifestos:
console.log(`A Cyborg Manifesto:  ${faveManifestos.cyborg}`);
```

This style of importing and exporting in JavaScript is known as **“named exports”** When you use named exports, you always need to wrap your imported names in curly braces

eg.

```
import {NavBar} from './NavBar.js'
class ProfilePage extends React.Component {
  render() {
    return (
      <div>
        __<NavBar />__
        <h1>All About Me!</h1>
        <p>I like movies and blah blah blah blah blah</p>
        <img src="https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-monkeyselfie.jpg" />
      </div>
    );
  }
}
```

---

## **this.props**

TL;DR

- Passing a prop by giving an attribute to a component instance
- Accessing a passed-in prop via this.props.prop-name
- Displaying a prop
- Using a prop to make decisions about what to display
- Defining an event handler in a component class
- Passing an event handler as a prop
- Receiving a prop event handler and attaching it to an event listener
- Naming event handlers and event handler attributes according to convention
- this.props.children
- getDefaultProps

### Access a Component's props

A component’s props is an object. It holds information about that component.

To see a component’s props object, you use the expression this.props. Here’s an example of this.props being used inside of a render method:

```
render() {
    return (
        <div>
            <h1> Hello this is {this.props.myProps} </h1>
        </div>
        )
}
ReactDOM.render(<PropsDisplayer myProp="Props ;D"/>, document.getElementById('app'))
```

### Pass `props` to a Component

```
//example
<Example message="This is some top secret info." />
//or
<MyComponent foo="bar" />
//or
<Greeting myInfo={["top", "secret", "lol"]} />
//or
<Greeting name="Frarthur" town="Flundon" age={2} haunted={false} />

```

### Pass props From Component To Component

Greeting.js Component

```
import React from 'react';

export class Greeting extends React.Component {
  render() {
    return <h1>Hi there, {this.props.name}!</h1>;
  }
}
```

App.js Component

```
//Don't forgeting import Component (named export)
import {Greeting} from './Greeting';
render() {
    return (
      <div>
        <h1>
          Hullo and, "Welcome to The Newzz," "On Line!"
        </h1>
        <Greeting name="Mark" />
        <article>
          Latest newzz:  where is my phone?
        </article>
      </div>
    );
  }
```

### Put an Event Handler in a Component Class

You can, and often will, pass functions as props. It is especially common to pass event handler functions.

```
handleEvent() {
    alert(`I am an event handler.
      If you see this message,
      then I have been called.`);
  }

  render() {
    return (
      <h1 onClick={this.handleEvent}>
        Hello world
      </h1>
    );
  }
```

or

```
//Button.js
render() {
    return (
      <button onClick={this.props.onClick}>
        Click me!
      </button>
    );
  }
```

```
//Talk.js
handleClick() {
    let speech = '';
    for (let i = 0; i < 10000; i++) {
      speech += 'blah ';
    }
    alert(speech);
  }

  render() {
    return <Button onClick={this.handleClick}/>;
  }
}
```

### handleEvent, onEvent, and this.props.onEvent

One major source of confusion is the fact that names like onClick have special meaning, but only if they’re used on HTML-like elements.

```
// Button.js

// The attribute name onClick
// creates an event listner:
<button onClick={this.props.onClick}>
  Click me!
</button>
```

```
// Talker.js

// The attribute name onClick
// is just a normal attribute name:
<Button onClick={this.handleClick} />
```

### this.props.children

```
<List>  // opening tag
  Hello // child
</List> // closing tag
```

if child have many list this.props.children will return an Array

```
<List>  // opening tag
  <li>a</li>
  <li>b</li>
  <li>c</li>
</List> // closing tag

//this.props.children === [<li>a</li>, <li>b</li>, <li>c</li>]
```

---

## this.state

There are two ways for a component to get dynamic information: props and state. Besides props and state, every value used in a component should always stay exactly the same.

### Setting Initial State

Unlike props, a component’s state is not passed in from the outside. A component decides its own state
This property should be **_"declared inside of a constructor"_** method, like this:

```
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = { mood: 'decent' };
  }

  render() {
    return <div>{this.state.mood}</div>;
  }
}

<Example />
```

**Note** : It is important to note that React components always have to call super in their constructors to be set up properly.

### Update state with this.setState({})

this.setState() takes two arguments: an object that will update the component’s state, and a callback. You basically never need the callback.

```
{
  mood:   'great',
  hungry: false
}
```

```
this.setState({ hungry: true });
```

```
{
  mood:   'great',
  hungry: true
}
```

**Note** : this.setState() takes an object, and merges that object with the component’s current state. If there are properties in the current state that aren’t part of that object, then those properties remain how they were.

### Call this.setState from Another Function

The most common way to call this.setState() is to call a custom function that wraps a this.setState() call. .makeSomeFog() is an example:

```
 constructor(props) {
    super(props);
    this.state = { mood: 'good' };
    this.toggleMood = this.toggleMood.bind(this);
  }

  toggleMood() {
    const newMood = this.state.mood == 'good' ? 'bad' : 'good';
    this.setState({ mood: newMood });
  }

  render() {
    return (
      <div>
        <h1>I'm feeling {this.state.mood}!</h1>
        <button onClick={this.toggleMood}>
          Click Me
        </button>
      </div>
    );
  }
```

You may have noticed a weird line in there:

```
this.makeSomeFog = this.makeSomeFog.bind(this);
```

.bind() can help method in obj or class pointing to this.obj not global obj, and for the less curious, just know that in React, whenever **_you define an event handler that uses_** this, you need to add `this.methodName = this.methodName.bind(this);`

---

**One final note** : you can’t call this.setState() from inside of the render function!, any time that you call this.setState(), this.setState() AUTOMATICALLY calls .render() as soon as the state has changed.

Think of this.setState() as actually being two things: this.setState(), immediately followed by .render().

That is why you can’t call this.setState() from inside of the .render() method! this.setState() automatically calls .render(). If .render() calls this.setState(), then an infinite loop is created.

---

# Interesting Code

```
constructor(props) {
    super(props);
    this.state = {
      password: 'swordfish',
      authorized: false
    };
    this.authorize = this.authorize.bind(this);
  }


  authorize(e) {
    const password = e.target.querySelector(
      'input[type="password"]').value;
    const auth = password == this.state.password;
    this.setState({
      authorized: auth
    });
  }
```
