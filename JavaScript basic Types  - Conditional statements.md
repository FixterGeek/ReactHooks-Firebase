![fixtergeek logo](https://fixter.camp/static/media/geek_completo.7e1e87a7.png)

## Javascript Primitives

#### What are you going to learn?

- What are the basic types of JavaScript
- How to manage these types in controll structures
- What is a conditional statement and how to type it
- Write your first JavaScript program

## Repl.it

![repl.it](https://repl.it/public/images/logo-small.png)

For this lesson we are going to use an online tool that will help us to see the inmediatly response of our code, call repl.it, this website allow us to write JavaScript directly in the browser in order to test the languaje, this website supports diferent languajes and frameworks, but we will use JavaScript this time.

## JavaScript types

In JavaScript the primitive types are very simple, we can find the same types as other languajes but simplified.

```javascript
let string = "BlisS";
let number = 7;
let boolean = true;
let noDefined;
let none = null;
let nan = 2 * "bliss";
```

#### Strings

In Javascript exists several native methods to work with this primitive "string" we can access to each character of the array using the index, or we can even convert a string into number, or into a controll structure like an array (we are going to talk about it in a second), you can use this tools like this:

```javascript
let name = "BlisS";
let age = "31";
console.log(name.split("")); // ["B", "l","i","s","S"]
console.log(name[3]); // s
console.log("Ye" + name[2] + "!!"); // Yei!!
console.log(parseInt(age)); // 31
console.log(typeof parseInt(age)); // number
```

We have one method that is very useful when we are looking for some letter inside an array this methods looks for the inclusion of this letter `includes`

```javascript
let name = "BlisS";

console.log(name.includes("s")); // true
```

#### Numbers

JavaScript has fully support for mathematics in a standarized way, it has several tools for working with maths, and all the basic operations are fully allowed. One thing to consider whe you work with numbers in JavaScript; is the fact that in JavaScript there are no such thing as int and float, just number, both are just number type.

```javascript
let num1 = 7,
  num2 = 10;
//sum
console.log(num1 + num2); // 17
console.log(num2 - num1); // 3
console.log(num1 * num2); // 70
console.log(num2 / num1); // 1.4285714...
console.log(num2 ** num1); // 10000000
console.log(num1 % num2); // 7
//the Math class
console.log(Math.PI); //3.141592653589793
console.log(Math.sqrt(16)); // 4
console.log(Math.sin(45)); // 0.8509035245341184
```

The `Math` class has a lot of tools in order to work with complex operations, these are just a few of them, if you want to know all the tools that the `Math` class supports you can read the official docs about it. [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

### Controll Structures

In JavaScript exists some other types that usually calls "controll structures" because we can store the primitives in those and manage it working with several variables and primitives in one place. JavaScript consider this structures a core concept and tool of the languaje, so we have a lot of methods to learn, methods and function that let us work with this structures, this structures are arrays `[]` and objects `{}`

```javascript
//arrays
let arrayOfNumbers = [1, 2, 3, 4, 5];
let mixinArray = [1, "blisS", false];
//objects
let simpleObject = {
  name: "BlisS",
  age: 31,
  active: true
};
let complexObject = {
  name: {
    firstName: "Héctor",
    lastName: "BlisS"
  },
  age: [1987, 04, 17],
  emails: [
    { value: "bliss@bliss.com" },
    { value: "bliss@gmail.com", active: false }
  ]
};
```

So, we can see these structures let us store a lot of information in just one variable, these structures are alse a type.

### Arrays

For year JavaScript has been depending in the arrays for one of the main pilar of the languaje, so JavaScript has a lot of methods that come automatically with the array type. We are going to use some of those methods in order to get familiar whit the arrays. There are several methods but, we will cover some of the most useful ones.

#### .forEach()

`forEach` is a loop that allow us to get every item in an array with out coding a conventional for loop, using the index, this method gives us the each element of the array and can gives us the index also in a separte variable, this method receives a function callback in order to know what to do with each element:

```javascript
let array = ["bliss", "fixter", "lol"];

array.forEach(function(element, index) {
  console.log(element, index);
});
```

#### .join()

the method join is simple, it can turn an array into a string.

```javascript
let array = ["Fixter", " ", "is", " ", "great"];

console.log(array.join("")); // "Fixter is great"
```

Join needs to have an empty string with `join('')` in order to work.

#### .push(), .unshift(), .shift(), .pop() and .indexOf()

We can work with the elements inside of an array, always working with its indexes and we have a bounch of methods that allow us to do it.
We can add items in the front of the array with `.unshift()` and in the tail with `.push()`, we can do exactly the opposite, we can remove elements from the front of the array with `.shift()` and in the tail with `.pop()`, we also can know what is the index of an element with `.indexOf()` as we can see in the example below.

```javascript
let array = ["bliss", "fixter"];

console.log(array.unshift("lol"));
// ["lol", "bliss", "fixter"]
console.log(array.push("JavaScript"));
//["lol", "bliss", "fixter", "JavaScript"]
console.log(array.shift());
//["bliss", "fixter", "JavaScript"]
console.log(array.pop());
//["bliss", "fixter"]
console.log(array.indexOf("bliss"));
// 0
```

#### .splice()

`.splice()` is a very powerful method of the arrays, it can work in two ways, we can use it to remove elements of the array, not only one element but several, and in any position inside the array not only the front and tail, but we can use it to add elements or several elements too, and also in any index of the array. In order to use it for remove elements we set the first argument that represents the index we want to remove, and the second argument indicates how many element we want to remove from this index (this is inclusive), and in order to add an element with `.splice()` we only have to add the 3rd argument that contains the element to add, it respect the 2 arguments before removing or substituing all those elements for the 3rd argument.

```javascript
let array = ["bliss", "fixter", "JavaScript"];

//remove
console.log(array.splice(0, 1)); // ["bliss"]
console.log(array); // ["fixter", "JavaScript"]

//add
console.log(array.splice(0, 0, "lol")); // ["lol", "fixter", "JavaScript"]
console.log(array.splice(0, 2, "yei")); // ["lol", "fixter"]
console.log(array); // ["yei", "JavaScript"]
```

All these methods return the element they remove or index they have worked with.

### Objects

The object is a comonly used way to store lots of information, even in a database, objects are more efficent with the system memory than the arrays because they are not orderer, and are more simply to work with, just a few methods that allow us to create, recover, modify and delete keys inside of them, the object use a system to store information called 'key value pair' it means that in order to store some primitive or other type of datan you need to name it with a keyname. This system remember us a dictionary.

```javascript
let person = {
  name: "Blis",
  age: 31,
  active: true
};

//reading data from key value pairs
console.log(person.name);
console.log(person["active"]);

//adding key value pairs
person.email = "bliss@bliss.com";
console.log(person);
person["tel"] = 7712;
console.log(person);

//modifying keys value pairs
let keyname = "tel";
person[keyname] = 888;
console.log(person);
person.age += 2;
console.log(person);

//removing
delete person.age;
console.log(person);
```

There are a class `Object` available to work in a modern way with the object type, [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) are the docs about the `Object` class, but the two main methods that we are going to use from this class are `Object.keys(person)` that returns an array of the object keys and `Object.values(person)` that returns an array of the object values.

### Loops and conditionals

Finally we are going to cover the conditionals in JavaScript mixing it with some modern loops of ECMAScript2015 (ES6), and we are about to finish with this super express summary of the JavaScript programming languaje.

#### The "if" statement

we can use `if(){}` to check if some expression resolves in a boolean type, can be also true or false, and we can use some operators like `==`, `===`, `<=`, `>=`, `!==` (the difference between the `==` and `===` is that the second checks for the type not only the characters), we can do something if the statement get a true resolution inside the block `{}` but also we can do something in case this if statement gets a false resolution with the second block `else{}`, and we always can concatenate more of one `if(){}` statement.

```javascript
if (true) {
  console.log("is always true");
}
//
let name = "bliss";
if (name === "luiss") {
  console.log("hey luiss");
} else {
  console.log("you are not luiss");
}
//
let num1 = 5;
if (num1 < 2) {
  console.log("you are small!");
} else if (num1 > 3) {
  console.log("you are greater!");
}
//
let num2 = 6;
let num3 = 2;
if (num2 % num3 === 0) {
  console.log("you are an even number");
} else {
  console.log("you are an odd number");
}
```

#### || and &&

We can use the operators and, or, to work with the `if(){}` statement, the result of the `&&` operator is true when both of the evaluating elements result in true, and the result of the `||` operator is true whe only one of the evaluating elements is true. These operators are very powerful and their use are very expreded in JavaScript and modern frameworks and we will work whith them in a more advance way in the future.

```javascript
let person = {
  name: "bliss",
  age: 31,
  active: true
};
if (person.name.includes("s") && person.age > 18) {
  console.log("you are allowed");
}

if (person.active || person.age < 18) {
  console.log("one of two");
}

if ((!person.active && person.age < 18) || name === "bliss") {
  console.log("yes, you can!");
}
```

We can combine them as many as we want.

#### Modern loops

We have the well know old friend `for(var i=0;i<10; i++>){}` statement, but we have a few other more modern that this one and may be more useful.

```javascript
let array = ["bliss", "fixter"];

for (let elem of array) {
  console.log(elem); // bliss, fixter
}

let object = { name: "bliss", age: 31 };

for (let key in object) {
  console.log(key); // name, age
  console.log(object[key]); // bliss, 31
}
```

"for of" let us get each element from an array, this works very similar to the forEach method, with the difference of this is not a method but a for statement.
The "for in" allow us to get each key in an object, this is very usefull in order to work with all the keys in an object, if we combine this for statements with the `Object` class: we can do very powerfull things.

## Recap:

We have cover a very rapid summary of the JavaScript languaje, just in order to start working with the JavaScript tools we will cover in this course in a more confident way. You are ready to give the next step, congratulations!.

## Resources:

- [More about JavaScript](https://www.javascript.com/)
- [The most modern and stable JavaScript](http://es6-features.org/#Constants)
- [JavaScript excercises - 10 days of JavaScript](https://www.hackerrank.com/domains/tutorials/10-days-of-javascript)

> Author: @hectorbliss
