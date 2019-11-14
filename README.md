# React From Scratch

Hello 👋,

So you've decided to learn React and came across this. This project is just a quick intro to React I threw together to help explain some simple concepts on how to _think and design in React_.

## 🚦 Before We Begin

### Who is this for?

This assumes you have a vague idea about what React is and you're intrerested in learning how to use the library without trying to find and gather resources or you want the quick version on how to get going.

### It's kind of a rubbish intoduction to React

That's fine, I'm not going to be showing this at conferences or anything. I'm just documenting the stuff I've shown others in the past and explained it in a way that seemed sensible to _me_ at least 😀. If you have a better way to explain a concept, feel free to fork and contribute.

### But seriously. Why?

I noticed that people tend to get bogged down in details like: _where is the view_ or _how does data get loaded_ or just _this is way too complex_ or _wtf is a JSX_. This intended to be a gentle introduction that I'll build up over time.

## 🎉 OK, Let's Get Started 

### Introduction, for real

So React is this cool Javascript library developed by Facebook to build user interfaces. It's very unopinionated about how to structure and architecture your project which in some cases can be why it seems to be very difficult to get started.

> This is not intended to be some kind of bible on how to build the world's best application in React. It just surfaces some patterns and thinking that I found worked well in the past (at least when I was learning).

### You will need

* A computer,
* a text editor, I recommend Visual Studio Code,
* NodeJS,

Caveat: I'm not going to explain ES5/ES6 modules, or _modern_ javascript development here. If you think I should while working through this, let me know.

### Create React App

To make setting up your project easier we're going to be using Create React App (CRA). CRA is a project developed by some really clever people at Facebook and the Open Source community to help bootstrap your project. Just like React itself it's fairly unopinionated about how you should do things and abstracts away a lot of the config and complexity. It suits 90% of use cases so its totally fine for us.

#### Install Create React App

We're going to use `npx` (https://www.npmjs.com/package/npx) to setup our first project. Inside a shell run the following commands:

```
    $ npx create-react-app my-project
    $ cd my-project
    $ npm run start
```

If everything has gone well, you should have a browser open automatically and navigate straight to http://localhost:3000. Great! we have a running application that can act as our scratch pad for the rest of this tutorial.

## 📦 Project Structure

Open the project in your editor and let's take a look at a couple of key files:

`src/index.js`

This is the main entry point for your application. Because we're starting from scratch, replace the module with the following:

```
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```

#### I love deleting stuff without explanation...

We removed some of the unnessary boilerplate so you can focus on the most important thing: ReactDOM. ReactDOM is basically the bootstrapper for your project. It manages mounting your entry point (in this case, `App`) into a specific DOM element (`root`).

In later tutorials we'll learn about how you can import other assets like CSS and what's actually happening under the hood.

#### Does the DOM element id have to be root?

Nope, the DOM element id can be whatever you want to call it. In this case, you can change it in the `index.html` file. Just make sure you update this `render` otherwise everything will blow up into 1,000 glittery pieces (not really but how cool would that be?).

#### Why is there HTML in my Javascript?

This is the secret React sauce also known as JSX. We'll have a look at this later but the short version is `<App />` is sweet, sweet syntactic sugar for `React.createElement('div');` just under the hood it's being translated for us.

`src/App.js`

We import this file in `index.js` and it serves as our entry point for the project. Once again we're starting from scratch so delete the contents of this file. And save it. Your file should look like this now:

```

```

Your browser should have blown up with an error. If that's happening... great! You're a React developer. Ok, not really next bit we're going to look at making our first component.

You'll notice your browser refreshes every time it saves. This happens in the background and maybe in the future we can take a look at super fancy things like _Hot Module Reloading_ which will replace components on the fly without reloading your whole app.

## 🍼 My First Component

Ok, so lets start with the basics. We're going to display your name (or maybe someone elses) in a paragraph. To do this we're going to need to import React and export a javascript function from this file:

`src/App.js`

```
import React from 'react';

const App = () => (
    <p>Hi Casey! 😎</p>
);

export default App;
```

#### So what's going on here?

All React components are either a function or a class (we'll look at classes when we're dealing with state later). Basically we're exporting a function that returns some HTML. - A super basic almost kernel-like component.

#### Now can we talk about HTML in JS?

Yep, so like I explained earlier JSX is basically HTML in Javascript but instead of _real_ HTML it's just a marker to tell the compiler that we need it to translate our code. This might be considered a weird anti-pattern but if you structure your code correctly it does eventually become second-nature. Short version: it's not really HTML.

#### Did it work?

Check it out in your browser, if everything worked, the error should be replaced by your greeting. Great job!

## 🏗 Make it a bit more useful

So... we now have a thing right? It's not really a interesting thing... just _something_. The Name Displayer 9000. Let's make it a bit more useful.

As you might have seen our components are a function. The function can take a single argument, an object, known as `props`. React works on a paradigm known as "data down, actions up". A component itself can't do much, it can receive values and _react_ (🥁) to that property change. Props themselves can be more or less any primitive.

In our Name Displayer component, lets set up our first prop. We're going to update our component:

`src/App.js`

```
const App = ({ name = 'Casey' }) => (
    <p>Hi {name}! 😎</p>
);

export default App;
```

As you can see in this example, we've now made name a variable and assigned it a default value.

When the page refreshes, you should see the component hasn't changed.

#### Sigh, what's this {name} stuff?

Inside a React component or HTML element, this is basically a way of displaying a value, in this case `name`. In later tutorials we can look at string interpolation and other tricks.

#### This is great, let's keep going

It's great but it's not useful, let's make some changes. We're going to build a few reusable components now but to do that we're going to reogranise things slightly:

`src/App.js`

```
const DisplayName = ({ name = 'Casey' }) => (
    <p>Hi {name}! 😎</p>
);

const App = () => (
    <DisplayName name='Kendra' />
);
```

What you should see now is we're saying hi to Kendra instead. We have our first component that we can now reuse. In fact, let's quickly do that now:

`src/App.js`

```
const DisplayName = ({ name = 'Casey' }) => (
    <p>Hi {name}! 😎</p>
);

const App = () => (
    <>
        <DisplayName />
        <DisplayName name='Kendra' />
        <DisplayName name='Stephen' />
        <DisplayName name='John' />
    </>
);
```

#### What does <>...</> mean?

Empty JSX is shorthand for `<React.Fragment>...</React.Fragment>` It's useful for when you have multiple components but don't want to wrap them in a DOM element like a `div`. This is because a function component can only return one element.

> As an interesting aside, React function components can return `null` or even strings.

#### Back to our component

Let's get back to working on our Name Displayer 9000 app. We're going to do another change to assign our name to a value:

`src/App.js`

```
const DisplayName = ({ name }) => (
    <p>Hi {name}! 😎</p>
);

const App = () => {

    const personsName = 'Casey';
    
    return <DisplayName name={personsName} />;

};
```

In our previous example we hard-coded the persons name. Now we're going to start focusing on being able to change the component with a input field. The first stage of the refactor is to just assign the name to a variable.

## 💾 State Management

Bed time...
