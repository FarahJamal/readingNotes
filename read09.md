I want to know more about Concepts of Functional Programming in Javascript
What is functional programming?
In computer science, functional programming is a programming paradigm where programs are constructed by applying and composing functions. It is a declarative programming paradigm in which function definitions are trees of expressions that map values to other values, rather than a sequence of imperative statements which update the running state of the program.

What is a pure function and how do we know if something is a pure function?
Pure Functions A pure function is a function which: Given the same input, will always return the same output. Produces no side effects

What are the benefits of a pure function?
Benefits of pure functions:

They’re easier to reason about
They’re easier to combine
They’re easier to test
They’re easier to debug
They’re easier to parallelize
What is immutability?
Immutables are the objects whose state cannot be changed once the object is created. Strings and Numbers are Immutable.

### What is Referential transparency?
Referential transparency and referential opacity are properties of parts of computer programs. An expression is called referentially transparent if it can be replaced with its corresponding value (and vice-versa) without changing the program's behavior.[1] This requires that the expression be pure, that is to say the expression value must be the same for the same inputs and its evaluation must have no side effects. An expression that is not referentially transparent is called referentially opaque.

### What are JS modules?
JS modules (also known as “ES modules” or “ECMAScript modules”) are a major new feature, or rather a collection of new features. You may have used a userland JavaScript module system in the past. Maybe you used CommonJS like in Node.js, or maybe AMD, or maybe something else. All of these module systems have one thing in common: they allow you to import and export stuff.

What does the word ‘require’ do?
require() is used to consume modules. It allows you to include modules in your app. You can add built-in core Node.js modules, community-based modules (node_modules), and local modules too.

### How do we bring another module into the file the we are working in?
by creating a JavaScript file. Every time you create a new file with .js extension, it becomes a module.

What do we have to do to make a module available?
The first thing you do to get access to module features is export them. This is done using the export statement.