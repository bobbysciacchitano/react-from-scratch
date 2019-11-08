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
* Yarn (optional).

I'm not going to explain what this all is here. But given you're working with Javascript you'll need NodeJS.

### Create React App

Create React App is a project developed by some really clever people at Facebook and the Open Source community to help bootstrap your project. Just like React itself it's fairly opinionated about how you should do things and abstracts away a lot of the config. It suits 90% of use cases so its _good enough_ for us.

#### Install Create React App

We're going to use `npx` to setup our first project. Inside a shell run the following commands:

```
    $ npx create-react-app my-project
    $ cd my-project
    $ npm run start
```

If everything has gone well, you should have a browser open automatically and navigate straight to http://localhost:3000. Great! we have a running application that can act as our scratch pad for the rest of this tutorial.

## 🍼 My First Component

### ...But first lets look at the structure



