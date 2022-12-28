[![Adarsh gupta](https://miro.medium.com/fit/c/96/96/1*t-ya5MdH4ALyrJ-TMnWneQ.png)

](https://adarsh-gupta.medium.com/?source=post_page-----18319669dade--------------------------------)[Adarsh gupta](https://adarsh-gupta.medium.com/?source=post_page-----18319669dade--------------------------------)[Follow](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2F_%2Fsubscribe%2Fuser%2F4323d7b9f6b1&operation=register&redirect=https%3A%2F%2Fblog.bitsrc.io%2Fthe-complete-javascript-guide-18319669dade&user=Adarsh+gupta&userId=4323d7b9f6b1&source=post_page-4323d7b9f6b1----18319669dade---------------------follow_byline-----------)

Oct 30

·6 min read

[

Save

](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2F_%2Fbookmark%2Fp%2F18319669dade&operation=register&redirect=https%3A%2F%2Fblog.bitsrc.io%2Fthe-complete-javascript-guide-18319669dade&source=--------------------------bookmark_header-----------)

The Complete JavaScript Guide
=============================

17+ topics, 5+ cheatsheets, 3+ hours of work
--------------------------------------------

pexels.com

To start using JavaScript, you only need this blog.

What is JavaScript
==================

JavaScript is a multi-paradigm, dynamic, high-level, loosely typed language.

We use JavaScript to create:

*   Websites
*   Mobile applications
*   Web applications
*   Server-side applications using Node.js
*   Smartwatch applications

Let now cover all the important JavaScript concepts, one-by-one

1\. Variable
------------

A variable is a value assigned to an identifier, so you can reference and use it later in the program.

We use the following keywords to declare variables:

`let`

`const`

`var`

2\. Types
---------

The type defines the data type of a particular variable or method.

Two main types of types in JavaScript:

• Primitive types

• object types

Primitive types are those which are either numbers or strings or booleans.

Object types are those which are either numbers or strings or booleans(if defined with the new keyword)

3\. Operators
-------------

In JavaScript, an operator is a special symbol used to perform operations on operands (values and variables).

The operators present in JavaScript are:

• Addition +

• Subtraction -

• Multiplication \*

• Division /

• modulus %

• Exponential \*\*

Comparison operators

<, >, <=, >=, ==, ===, !==

4\. Conditionals
----------------

Conditional statements control behavior in JavaScript and determine whether or not pieces of code can run.

```
if(true){ condition}
```

Loops

```
While loop: while(true){}For Loop: for(s1,s2,s3){//statements}Do while: do{}while(true)
```

5\. Complete loop Cheatsheet

6\. Arrays
----------

An array is a collection of similar data elements stored at contiguous memory locations

```
const array=\[1,2,3\]
```

**Array Operations**

```
push() : Add to arraypop() : remove from arrayconcat() : join 2 arrays
```

7\. Hoisting
------------

When developers are unclear about the concept of hoisting in JavaScript, they frequently encounter unexpected outcomes. Before the execution of the code, the interpreter appears to move the declaration of functions, variables, or classes to the top of their scope.

8\. Functions
-------------

lines of code for doing a specific task.

A function in JavaScript is similar to a procedure—a set of statements that perform a task or calculate a value—but for a procedure to qualify as a function, it should take some input and return an output where there is some obvious relationship between the input and the output(according to MDN docs).

9\. Arrow functions
-------------------

They allow you to write functions with a shorter syntax.

10\. Complete functions Cheatsheet
----------------------------------

11\. Scope
----------

Scope defines whether you can access or reference a particular value or expression. We are unable to use a declared variable if it is not included in the current scope. This idea is crucial to understand because it makes it easier to separate logic in your code.

In JavaScript, we have 3 types of scopes:

**Global scope**: Variables and expressions can be referred to anywhere in a global scope. This is the default scope.

**Local scope**: variables and expressions can be referenced only within the boundary.

12\. Objects
------------

Any value that’s not of a primitive type is always passed by reference.

13\. Classes
------------

Class methods are created with the same syntax as object methods. Use the keyword class to create a class.

Classes are a template for creating objects.

14\. Callbacks
--------------

A callback is a function that is passed as an argument to another function, and its execution is delayed until that function to which it is passed is executed.

15\. Promises

A promise is an object that has the potential to produce only one value in the future: either a resolved value or an explanation for why it cannot be resolved (such as a network error).

There are three possible states for a promise: fulfilled, rejected or pending

16\. Asynchronous JavaScript
----------------------------

Asynchronous JavaScript has never been easy. We have used callbacks for a while. Then, we made promises. We use asynchronous functions most of the time now.

17\. Closure
------------

It is a feature in JavaScript where an inner function has access to the outer function’s variables

The inner function can access the variables defined in its scope, the scope of its parent functions, or even its grandparent functions and the global variables.

```
function grandparent() {  
    let car="BMW"  
    var parent = function () {  
        let house="4BHK"  
        var child = function () {  
            return ("The child gets " + car + " and " + house);  
        };  
        return child;  
    };  
    return parent;  
}  
  
console.log( grandparent()()()) //The Child gets BMW and 4BHK house
```

Wrapping it up
--------------

It’s a strange language, JavaScript. But when you look closer, you typically understand why things operate that way.

I sincerely hope that this list will help you understand some of the crucial JavaScript concepts that you should know, and if you are aware of any additional concepts that are noteworthy, please mention them in the comments section :)

Check out this e-book for a complete [CSS Flexbox guide](https://gumroad.com/a/381209427/GHwFS).

This guide took several hours to create, and several resources have been referenced. If you find this Guide useful, Share and spread the word

Follow me, [Adarsh gupta](https://medium.com/u/4323d7b9f6b1?source=post_page-----18319669dade--------------------------------) on Medium as well as on Twitter (@[Adarsh\_\_\_\_gupta](http://twitter.com/adarsh____gupta)).

[If you wish, you can support me b](https://www.buymeacoffee.com/Adarshgupta)y [buying me a Chai.](https://www.buymeacoffee.com/Adarshgupta)

Go composable: Build apps faster like Lego
==========================================

[](https://bit.cloud)

[**Bit**](https://bit.cloud) is an open-source tool for building apps in a modular and collaborative way. Go composable to ship faster, more consistently, and easily scale.

**→** [Learn more](https://bit.dev)

Build apps, pages, user-experiences and UIs as standalone components. Use them to compose new apps and experiences faster. Bring any framework and tool into your workflow. Share, reuse, and collaborate to build together.

Help your team with:

**→** [**Micro-Frontends**](https://medium.com/how-we-build-micro-front-ends-d3eeeac0acfc)

**→** [**Design Systems**](https://medium.com/how-we-build-our-design-system-15713a1f1833)

**→** [**Code-Sharing and reuse**](https://bit.cloud/blog/how-to-reuse-react-components-across-your-projects-l4pz83f4)

**→** [**Monorepos**](https://www.youtube.com/watch?v=5wxyDLXRho4&t=2041s)

Learn more
==========

[

How We Build Micro Frontends
----------------------------

### Building micro-frontends to speed up and scale our web development process.

blog.bitsrc.io

](https://medium.com/how-we-build-micro-front-ends-d3eeeac0acfc)[

How we Build a Component Design System
--------------------------------------

### Building a design system with components to standardize and scale our UI development process.

blog.bitsrc.io

](https://medium.com/how-we-build-our-design-system-15713a1f1833)[

How to reuse React components across your projects
--------------------------------------------------

### Finally, you completed the task of creating a fantastic input field for the newsletter in your app. You are happy with…

bit.cloud

](https://bit.cloud/blog/how-to-reuse-react-components-across-your-projects-l3bhezsg)[

5 Ways to Build a React Monorepo
--------------------------------

### Build a production-grade React monorepo: From fast builds to code-sharing and dependencies.

blog.bitsrc.io

](https://medium.com/5-ways-to-build-a-react-monorepo-a294b6c5b0ac)[

How to Create a Composable React App with Bit
---------------------------------------------

### In this guide, you’ll learn how to build and deploy a full-blown composable React application with Bit. Building a…

bit.cloud

](https://bit.cloud/blog/how-to-create-a-composable-react-app-with-bit-l7ejpfhc)
