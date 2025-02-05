# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Imagine you are teaching a friend about OOP. They mainly want to understand what is Encapsulation. Write a brief lesson on Encapsulation that includes the following:

- What is encapsulation?
- What major goal does this help to achieve in software engineering?
- Give an example (in code) of encapsulation.
- An explanation of how the code example demonstrates encapsulation

### Response 1

## Prompt 2

The following `friendsManager` object is an example of an interface that is **NOT** consistent and predictable:

```js
const friendsManager = {
  friends: [],
  addFriend(newFriend) {
    if (typeof newFriend !== "string") return;
    this.friends.push(newFriend);
  },
};

friendsManager.addFriend("daniel");
friendsManager.addFriend(true);
friendsManager.friends.push("emmaneul");
friendsManager.friends.push(42);
```

Explain how the code is not consistent or predictable, then provide an example in code that uses closure to make it more consistent and predictable.

### Response 2

## Prompt 3

With OOP in JavaScript, it's possible to use factory functions to achieve encapsulation and re-use them to make objects that look alike. However, factory functions have drawbacks and we often use classes instead.

How would you explain to a budding developer what the drawbacks of using factory functions are and why it is better to use classes instead?

### Response 3

## Prompt 4

Do some research on the history of when / how classes were introduced into JavaScript and share your findings. Your response should include:

- What version of JavaScript were classes introduced in and when did it come out?
- Why were classes introduced into JavaScript?

### Response 4

Classes were introduced in ECMAScript 2015 (ES6), which was released in June 2015. JavaScript already had prototype-based inheritance, but it was more verbose and unintuitive, especially for developers coming from class-based (OOP) languages like Python or C++. With classes, methods are automatically added to the prototype, reducing memory usage, and there’s no need to manually assign methods inside a constructor, making code easier to read, reuse, and debug. This makes large projects more manageable. The constructor, extends, and super keywords made it simpler to create and extend objects with clear relationships, providing syntactic sugar for prototypes. In other words, classes provide a clearer, more intuitive syntax for creating and extending objects.

### Notes for Beginners:

- Classes: A class is like a blueprint for creating objects. Instead of manually creating each car, a class lets you define a template

- Objects: In JavaScript, an object is a collection of related information. Think of it like a box that holds data (like a name or color) and actions (things it can do). For example, a "car" object could have:

```js
let car = {
  color: "red", // Here, color is a property,
  drive: function () {
    // and drive() is a method (an action the car can perform).
    console.log("The car is moving");
  },
};
```

- Prototype: A built-in system in JavaScript that allows objects to share features without copying them. Instead of every car object having its own separate copy of drive(), JavaScript stores it in a shared prototype so all cars can use the same function. This saves memory and keeps code efficient.

- Constructor: A special function inside a class that runs when you create a new object. It's like a blueprint that tells JavaScript how to build each object.

- Inheritance: A way for one object to get properties and actions from another object. For example, if "Car" is a class, a "Tesla" class could inherit everything from "Car" while adding its own unique features.

- Extends: A keyword in JavaScript that lets one class get features from another, like saying, "Tesla is a type of Car."
  Super: A keyword used inside an extended class to refer to the original class. If "Tesla" extends "Car," super() helps access Car’s setup.

- Syntactic sugar: A way to write code more clearly without changing how it works behind the scenes. JavaScript classes don’t introduce new functionality—they just make existing features easier to use.

## Prompt 5

OOP can still be achieved in JavaScript without using the `class` keyword and instead using the "Constructor Functions" and the "Prototype Chain" (look them up!)

```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function () {
  return `Hi, I'm ${this.name}, and I'm ${this.age} years old.`;
};

const alice = new Person("Alice", 30);
console.log(alice.greet());
```

Provide one point that advocates for the use of this syntax and then provide a counter-argument for the use of classes instead.

### Response 5

Using Constructor Functions gives you more control over how objects work, allowing manual setup of inheritance and methods. This can be helpful for small projects or custom setups.

Classes make the code cleaner and easier to read. You don’t need to manually set up the prototype or methods—they’re automatically handled. This is especially useful as the project grows or if you come from other OOP languages. It reduces repetitive code and makes the logic clearer.

In the code example, methods are added to the prototype manually, which makes the code longer. Using a class automatically includes the methods, making the code shorter and easier to understand. A class also automatically binds methods to the prototype, which makes the code easier to extend and maintain by keeping it cleaner and more organized.
