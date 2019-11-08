# react-from-scratch

Hello 👋,

So you've decided to learn React and came across this. This project is just a quick intro to React I threw together to help explian some simple concepts on how to _think and design in React_.

## 🚦 Before We Begin

### Who is this for?

This assumes you have a vague idea about what exactly React is and you're intrerested in learning how to use the library without trying to find and gather resources or you want the quick version on how to get going.

### It's kind of a rubbish intoduction to React

That's fine, I'm not going to be showing this at conferences or anything. I'm just putting the stuff I've shown others in the past and explained it in a way that seemed sensible to _me_ at least 😀. If you have a better way, feel free to fork an contribute.

### But seriously. Why?

I noticed that people tend to get bogged down in details like: _where is the view_ or _how does data get loaded_ or just _this is way too complex_ or _wtf is a JSX_. This intended to be a gentle introduction that I'll build up over time.

## 🎉 OK, Let's Get Started 

### Introduction, for real

So React is this cool Javascript library developed by Facebook which is intended to basically provide you with a mechanism to easily add interactivity to your browser UI. It's very unopinionated about how to structure and architecture your project which in some cases can be why it seems to be very difficult to get started.

> This is not intdended to be some kind of bible on how to build the world's best application in React. It just surfaces some patterns and thinking that I found worked well in the past (at least when I was learning).

### You will need

* A computer,
* a text editor, I recommend Visual Studio Code,
* NodeJS,

Caveat: I'm not going to explain ES5/ES6 modules, or _modern_ javascript development here. If you think I should while working through this, let me know.

### Create React App

Create React App is a project developed by some really clever people at Facebook and the Open Source community to help bootstrap your project. Just like React itself it's fairly opinionated about how you should do things and abstracts away a lot of the config. It suits 90% of use cases so its totally fine for us.

#### Install Create React App

We're going to use `npx` to setup our first project. Inside a shell run the following commands:

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

#### I love deleting stuff without knowing what I'm doing...

We removed some of the unnessary boilerplate so you can focus on the most important thing: ReactDOM. ReactDOM is basically the bootstrapper for your project. It manages mounting your entry point (in this case, `App`) into a specific DOM element (`root`).

In later tutorials we'll learn about how you can import other assets like CSS and what's actually happening under the hood.

#### Does the DOM element id have to be root?

Nope, the DOM element can be whatever you want to call it. In this case, you can change it in the `index.html` file. Just make sure you update this file otherwise everything will blow up into 1,000 glittery pieces (ok not really but how cool would that be?).

#### Why is there HTML in my Javascript?

This is the secret React sauce also known as JSX. We'll have a look at this later but the short version is `<App />` is sweet, sweet syntactic sugar for `React.createElement('div');` just under the hood it's being translated for us.

`src/App.js`

We import this file in `index.js` and it serves as our entry point for the project. Once again we're starting from scratch so delete the contents of this file. And save it. Your file should look like this now:

```

```

Your browser should have blown up with an error. If that's correct then great! You're a React developer. Ok, not really next bit we're going to look at making our first component.

You'll notice your browser refreshes every time it saves. This happens in the background and maybe in the future we can take a look at super fancy things like _Hot Module Reloading_ which will replace components on the fly without reloading the whole screen.

## 🍼 My First Component

Ok, so lets start with the basics. We're going to display you're name (or maybe someone elses) in a paragraph. To do this we're going to need to import React and create a javascript function:

`src/App.js`

```
import React from 'react';

export default App = () => (
    <p>Hi Casey! 😎</p>
);
```

### So what's going on here?

All React components are either a function or a class (we'll touch on this later). 

We're importing React to the project to tell the transpiler that it needs to translate the JSX syntax into something else. `export default` means our function component is the only thing we're exposing to the world.

Alternatively, if you want to export multiple components you can use `export const App` and then `import { App } from './App';` instead. I tend to find one module per file is a bit easier to manage.

### Now can we talk about HTML in JS?

Yep, so like I explained earlier JSX is basically HTML in Javascript but instead of _real_ HTML it's just a marker to tell the compiler that we need it to translate our code. This might be considered a weird anti-pattern but if you structure your code correctly it does eventually become second-nature. Short version: it's not really JS.

### Did it work?

Check it out in your browser, if everything worked, the error should be replaced by your greeting. Great job!

