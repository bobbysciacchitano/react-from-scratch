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

---

`src/index.js`

This is the main entry point for your application. Because we're starting from scratch, replace the module with the following:

```
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```

#### I love deleting stuff without knowing what I'm doing...

We removed some of the unnessary boilerplate so you can focus on the most important thing. ReactDOM is basically the bootstrapper for your project. It manages mounting your entry point (in this case `App`) into a specific DOM element (`root`).

In later tutorials we'll learn about other assets like CSS and what's actually happening under the hood.

#### Does the DOM element id have to be root?

Nope, the DOM element can be whatever you want to call it. In this case, you can change it in the `index.html` file. Just make sure you update this file otherwise everything will blow up into 1,000 glittery pieces (ok not really but how cool would that be?).

#### Why is there HTML in my Javascript?

This is the secret React sauce also known as JSX. We'll have a look at this later but the short version is `<App />` is sweet, sweet syntactic sugar for `React.createElement('div');` just under the hood it's being translated for us.

---

`src/App.js`

We import this file in `index.js` and it serves as our entry point for the project. Once again we're starting from scratch so delete the contents of this file. And save it. Your file should look like this now:

```

```

And your browser should have blown up with an error. If that's correct then great! You're a React developer. Ok, not really next bit we're going to look at making our first component.

## 🍼 My First Component

Ok, so lets start with the basics. We're going to display you're name (or maybe someone elses) in a paragraph. 