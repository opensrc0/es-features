<h1 align="center">Different ES features according to ES release</h1>
<br />

Every year ES is releasing different features and those features will be available in javascript. Most of the browser are providing the support but chrome is the source of trust of newly available feature.


# Table of contents
1. [ES2015 || ES6](#ES2015-ES6)
2. [ES2016 || ES7](#ES2016-ES7)
3. [ES2017 || ES8](#ES2017-ES8)
4. [ES2018 || ES9](#ES2018-ES9)
5. [ES2019 || ES10](#ES2019-ES10)
6. [ES2020 || ES11](#ES2020-ES11)
7. [ES2021 || ES12](#ES2021-ES12)
8. [ES2022 || ES13](#ES2022-ES13)

## ES2015-ES6

----

All fetures Referance: https://github.com/lukehoban/es6features

###### 1.1) Arrows
---
- Arrows are a function shorthand using the => syntax.
- An arrow function expression is a compact alternative to a traditional function expression, but is limited and can't be used in all situations
- Does not have its own bindings to this or super, and should not be used as methods
- Does not have arguments,
- Not suitable for call, apply and bind methods
- Can not be used as constructors.
- Can not use yield, within its body.

```javascript
// Expression bodies
var odds = evens.map(v => v + 1);
var nums = evens.map((v, i) => v + i);
var pairs = evens.map(v => ({even: v, odd: v + 1}));
// Statement bodies
nums.forEach(v => {
  if (v % 5 === 0)
    fives.push(v);
});
// Lexical this
var bob = {
  _name: "Bob",
  _friends: [],
  printFriends() {
    this._friends.forEach(f =>
      console.log(this._name + " knows " + f));
  }
}
```

###### 1.2 Classes
---
- ES6 classes are a simple sugar over the prototype-based OO pattern
- JavaScript Classes are templates for JavaScript Objects.
- Use the keyword class to create a class.
- Always add a method named constructor():

```javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}
```

###### 1.3 Enhanced Object Literals
---

```javascript
// ES5 code
var a = 1, b = 2, c = 3;
var  obj = {
    a: a,
    b: b,
    c: c
  };
// obj.a = 1, obj.b = 2, obj.c = 3

// ES6 code
const
  a = 1, b = 2, c = 3;
  obj = {
    a
    b
    c
  };

// obj.a = 1, obj.b = 2, obj.c = 3

// ES6 code
const
  i = 1,
  obj = {
    ['i' + i]: i
  };

console.log(obj.i1); // 1
```

######  1.4) Template Strings
---
Template strings provide syntactic sugar for constructing strings

```javascript
// Basic literal string creation
`In JavaScript '\n' is a line-feed.`

// String interpolation
var name = "Bob", time = "today";
`Hello ${name}, how are you ${time}?`
```

######  1.5 Destructuring
---
The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.

```javascript
let arr = ["John", "Smith"]
let [firstName, surname] = arr;
alert(firstName); // John
alert(surname);  // Smith
```

######  1.6)  Default + Rest + Spread
---
```javascript
function f(x, y=12) {
  // y is 12 if not passed (or passed as undefined)
  return x + y;
}
f(3) == 15

function f(x, ...y) {
  // y is an Array
  return x * y.length;
}
f(3, "hello", true) == 6

function f(x, y, z) {
  return x + y + z;
}
// Pass each elem of array as argument
f(...[1,2,3]) == 6
```

######  1.7) Let + Const
---

######  1.8) Generators
---

###### 1.9) Unicode
---

###### 1.10) Modules
---

Language-level support for modules for component definition.
```javascript
// app.js
import * as math from "lib/math";
alert("2π = " + math.sum(math.pi, math.pi));
```

###### 1.11) Module Loaders
---

###### 1.12) Map + Set + WeakMap + WeakSet
---

###### 1.13) Proxies
---

###### 1.14) Symbols
---

###### 1.15) Math + Number + String + Array + Object APIs
---

###### 1.16) Tail Calls
---

######  1.17) Promises
---

###### 1.18) Binary and Octal Literals
---

###### 1.19) Subclassable Built-ins
---


## ES2016-ES7
---
Referance: https://github.com/daumann/ECMAScript-new-features-list/blob/master/ES2016.MD

######  2.1 ) Array.prototype.includes()
---

The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate.

```javascript
let numbers = [1, 2, 3, 4];
// ES 6 before
if(numbers.indexOf(2) !== -1) {  console.log('Array contains value');}
// ES 6 after
if(numbers.includes(2)) {  console.log('Array contains value');}
```

###### 2.2) Exponential Operator:
---

3 ** 3
O/P: 27

```javascript
let cubed = x => x ** 3;
cubed(2) // 8
```

###### 2.3) Class Properties :
---

```javascript
class Animal {
    constructor() {
        this.name = "Lion"
    }
    age = 0;
}

That will be complied to:
    class Animal {
        constructor() {
            this.age = 0;
            this.name = "Lion";
        }
    }
Especially react developers can relate easily state! and initialProps!:
    class Animal {
        constructor() {
            this.name = "Lion"
        }
        age = 0;
        state = {
        }
        initialProps = {
        }
    }
```


## 3) ES2017-ES8
---
https://github.com/daumann/ECMAScript-new-features-list/blob/master/ES2017.MD

###### 3.1)  async function
---

- "async and await make promises easier to write"
- async makes a function return a Promise
- await makes a function wait for a Promise

```javascript
function resolveAfter2Seconds() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve('resolved');
    }, 2000);
  });
}

async function asyncCall() {
  console.log('calling');
  const result = await resolveAfter2Seconds();
  console.log(result);
  // expected output: "resolved"
}

asyncCall();
```
The await keyword is only valid inside async functions within regular JavaScript code. If you use it outside of an async function's body, you will get a SyntaxError.

###### 3.2) Object.entries()
---
JavaScript Object.entries() method is used to return an array of a given object's own enumerable property [key, value] pairs

```javascript
var fruits = {
    apple: 10,
    orange: 20,
    grapes: 30,
    pineapple: 40
}

 Object.entries(fruits);
 O/P // => [ ["apple", 10], ...etc ]

for (var [key, val] of Object.entries(fruits)) {
    console.log(key, val);
}
Output:
apple 10
orange 20
grapes 30
pineapple 40

```

###### 3.3) Object.values()
---

Object.values lets us return an array of a given object's own enumerable property values. Note that the order is the same as provided by the for...in loop.

```javascript
var fruits = {
    apple: 10,
    orange: 20,
    grapes: 30,
    pineapple: 40
}

Object.values(fruits)
O/P [10, 20, 30, 40]

var totalVegetables = Object.values(fruits).reduce((a, b) => a + b);
console.log(totalVegetables);
Output: 100
```

###### 3.4) Object.getOwnPropertyDescriptors()
---

Object.getOwnPropertyDescriptors() returns all own property descriptors of a given object
A property descriptor is a record with one of the
- value
- writable
- get
- set
- configurable
- enumerable

```javascript
let myObj = {
  property1: 'foo',
  property2: 'bar',
  property3: 42,
  property4: () => console.log('prop4')  
}

Object.getOwnPropertyDescriptors(myObj)
/*
{ property1: {…}, property2: {…}, property3: {…}, property4: {…} }
  property1: {value: "foo", writable: true, enumerable: true, configurable: true}
  property2: {value: "bar", writable: true, enumerable: true, configurable: true}
  property3: {value: 42, writable: true, enumerable: true, configurable: true}
  property4: {value: ƒ, writable: true, enumerable: true, configurable: true}
  __proto__: Object
*/
```

###### 3.5) Trailing Commas
---

```javascript
var list = [
    "one",
    "two",
    "three",   // It is valid
]

const func = (a,b,c,) => {
  // no error occurs
};
```

######  3.8) string.padEnd() and string.padStart() functions:
----

```javascript
'1'.padStart(3, 0);
O/P: "001"

'1'.padEnd(5, 0);
O/P: "10000"
```

### 4) ES2018-ES9
---

https://github.com/daumann/ECMAScript-new-features-list/blob/master/ES2018.MD

###### 4.1) Async iterators
---

Asynchronous iteration allow us to iterate over data that comes asynchronously, on-demand.
Like, for instance, when we download something chunk-by-chunk over a network. And asynchronous generators make it even more convenient.

```javascript
function asyncIterator() {
  const array = [1, 2];
  return {
    next: function() {
      if (array.length) {
        return Promise.resolve({
          value: array.shift(),
          done: false
        });
      } else {
        return Promise.resolve({
          done: true
        });
      }
    }
  };
}

var iterator = asyncIterator();

(async function() {
    await iterator.next().then(console.log); // { value: 1, done: false }
    await iterator.next().then(console.log); // { value: 2, done: false }
    await iterator.next().then(console.log); // { done: true }
})();
```

###### 4.2) Object rest properties
---

Rest properties for object destructuring assignment.

```javascript
let { fname, lname, ...rest } = { fname: "Hemanth", lname: "HM", location: "Earth", type: "Human" };
fname; //"Hemanth"
rest; // {location: "Earth", type: "Human"}
```

###### 4.3) Object spread properties
---

Spread properties for object destructuring assignment.

```javascript
let info = {fname, lname, ...rest};
info; // { fname: "Hemanth", lname: "HM", location: "Earth", type: "Human" }
```

###### 4.4) Promise prototype finally
---

Promise API is extended by an optional finally block which is called in any case (after the Promise is resolved or is rejected).

```javascript
function testFinally() {
  return new Promise((resolve,reject) => resolve())
}

testFinally().then(() => console.debug("resolved")).finally(() => console.debug("finally"))
// resolved
// finally
```

## 5)  ES2019-ES10
---

https://dev.to/prabusubra/es2019-es10-features-5b14

###### 5.1) Array.prototype.{flat,flatMap}
---

```javascript
The flat() method enables you to easily concatenate all sub-array elements of an array. Consider the following example:

arr = [10, [20, [30]]];

console.log(arr.flat());     // => [10, 20, [30]]
console.log(arr.flat(1));    // => [10, 20, [30]]
console.log(arr.flat(2));    // => [10, 20, 30]
```
The flatMap() method combines map() and flat() into one method.
It first creates a new array with the return value of a provided function and then concatenates all sub-array elements of the array.

```javascript
console.log(arr.map(value => [Math.round(value)]));    
// => [[4], [20], [26]]

console.log(arr.flatMap(value => [Math.round(value)]));    
// => [4, 20, 26]
```

###### 5.2) Object.fromEntries
---

This static method allows you to easily transform a list of key-value pairs into an object:

```javascript
const myArray = [['one', 1], ['two', 2], ['three', 3]];
const obj = Object.fromEntries(myArray);
console.log(obj);    // => {one: 1, two: 2, three: 3}
```

###### 5.3)  String.prototype.{trimStart,trimEnd}
---

The trimStart() and trimEnd() methods are technically the same as trimLeft() and trimRight(). These methods are currently stage 4 proposals and will be added to the specification for consistency with padStart() and padEnd(). 

```javascript
const str = "   string   ";

// es2019
console.log(str.trimStart());    // => "string   "
console.log(str.trimEnd());      // => "   string"

// the same as
console.log(str.trimLeft());     // => "string   "
console.log(str.trimRight());    // => "   string"
```

###### 5.4) Symbol.prototype.description
---

When creating a Symbol, you can add a description to it for debugging purposes. Sometimes, it’s useful to be able to directly access the description in your code.

This ES2019 proposal adds a read-only description property to the Symbol object, which returns a string containing the description of the Symbol. Here are some examples:

```javascript
let sym = Symbol('foo');
console.log(sym.description);    // => foo

sym = Symbol();
console.log(sym.description);    // => undefined

// create a global symbol
sym = Symbol.for('bar');
console.log(sym.description);    // => bar
```

###### 5.5) Optional catch binding
---

This makes a small change to the ECMAScript specification that allows you to omit the catch binding and its surrounding parentheses:

```javascript
try {
  // use a feature that the browser might not have implemented
} catch {
  // do something that doesn’t care about the value thrown
}
```


## ES2020-ES11
---

https://areknawo.com/ecmascript-2020-biggest-new-features/
https://dev.to/aryclenio/the-new-features-of-javascript-in-2020-es11-7jc

###### 6.1) BigInt
---

The biggest integer "usual" number type can handle is equal to 2 ** 53 - 1 or 9007199254740991. You can access this value under the MAX_SAFE_INTEGER constant.

```javascript
Number.MAX_SAFE_INTEGER; // 9007199254740991
```

###### 6.2) Dynamic import
---

Now, with Javascript, we can import modules dynamically through variables. With that, the variables that receive the modules are able to encompass the namespaces of these modules in a global way.

```javascript
import("module.js").then((module) => {
  // ...
});
// or
async () => {
  const module = await import("module.js");
};
```

```javascript
let Dmodule;

if ("module 1") {
  Dmodule = await import('./module1.js')
} else {
  Dmodule = await import('./module2.js')
}

/* It is possible to use Dmodule. (Methods)
throughout the file globally */
Dmodule.useMyModuleMethod()
```


###### 6.3) Exporting modules
---
A new syntax was added allowing the export of modules similar to import that already existed, see an example below:

```javascript
// Existing in JS
import * as MyComponent from './Component.js'
// Added in ES11
export * as MyComponent from './Component.js'
```

###### 6.4) Optional Chaining
---

Optional Chaining, known to babel users, is now supported natively by Javascript

```javascript
const user = {
  "name": "Aryclenio Barros",
  "age": 22,
  "alive": true,
  "address": {
    "street": "Hyrule street",
    "number": 24,
  }
}
// Without optional chaining
const number = user.address && user.address.number
// With optional chaining
const number = user.address?.number
```

###### 6.5) Nullish coalescing operator
---

Now we're starting to talk about some truly new stuff! Nullish coalescing operator (??) is a new JS operator allowing basically to provide a "default value" when the accessed one is either null or undefined. Check it out:

```javascript
const basicValue = "test";
const nullishValue = null;
const firstExample = basicValue ?? "example"; // "test"
const secondExample = nullishValue ?? "example"; // "example"
```

###### 6.6) Promise.AllSettled
---

The Promise.AllSettled attribute allows you to perform a conditional that observes whether all promises in an array have been resolved

```javascript
const myArrayOfPromises = [
    Promise.resolve(myPromise),
    Promise.reject(0),
    Promise.resolve(anotherPromise)
]

Promise.AllSettled(myArrayOfPromises).then ((result) => {
   // Do your stuff
})
```

###### 6.7) String.matchAll()
---

Basically, if you've ever worked with RegExps before, String.matchAll() is a nice alternative to using RegExp.exec() in a while loop with the g flag enabled. That's all there's to it. It returns an iterator (not to be confused with full-blown arrays) that contains all the match results - including capturing groups.

```javascript
const regexp = /t(e)(st(\d?))/g;
const str = "test1test2";
const resultsArr = [...str.matchAll(regexp)]; // convert iterator to an array

resultsArr[0]; // ["test1", "e", "st1", "1"]
resultsArr[0]; // ["test2", "e", "st2", "2"]
```

###### 6.8) For-in order
---

Lastly, we've got just a minor tweak to the specs that now strictly defines the order in which the for..in loop should iterate. It was already handled pretty well by the browsers themselves, so it's just a matter of making it official.


## ES2021-ES12
---
https://dev.to/brayanarrieta/new-javascript-features-ecmascript-2021-with-examples-3hfm

###### 7.1) Numberic separators
---
Numberic separators
Allows numeric literals use underscores as separators to help to improve readability

```javascript
// A billion
const amount = 1_000_000_000;

// Hundreds of millions     
const amount = 1_475_938.38;
```


###### 7.2) String.protype.replaceAll
---

Currently, there is no way to replace all instances of a substring without the use of global regexp (/regex/g)

```javascript
Before (with regex)
const message = 'hello+this+is+a+message';
const messageWithSpace = message.replace(/\+/g, ' ');
// hello this is a message

```

```javascript
After (with new method replaceAll)
const message = 'hello+this+is+a+message';
const messageWithSpace = message.replaceAll('+', ' ')

// hello this is a message
```


###### 7.3) Logical assignment operator
---

There are some new operators:

And & Equals (&&=)
OR & Equals (||=)
Nullish Coalescing & Equals (??=)


```javascript
let a = 1;
if(a){
  a = 8;
}

// Output: a = 8
```

```javascript
let a = 1;
a &&= 3

// Output: a = 3
```

```javascript
//Before
// If conditional
let a = undefined;
if(!a){
  a = 5;
}

// Output: a = 5

// OR
a = a || 3;

// Output: a = 3

```

```javascript
// After
let a = 0;
a ||= 3

// Output: a = 3

```

```javascript
//Nullish Coalescing & Equals (??=)
//Assign when the value is null or undefined.
let a = undefined; 
a ??= 7

// Output: a = 7
```

###### 7.4) Promise.any method
---

```javascript
const firstPromise = new Promise((resolve, reject) => {
  setTimeout(() => reject(), 1000);
});

const secondPromise = new Promise((resolve, reject) => {
  setTimeout(() => reject(), 2000);
});

const thirdPromise = new Promise((resolve, reject) => {
  setTimeout(() => reject(), 3000);
});

try {
  const first = await Promise.any([
    firstPromise, secondPromise, thirdPromise
  ]);
  // Any of the promises was fulfilled.
} catch (error) {
  console.log(error);
  // AggregateError: All promises were rejected
}
```

###### 7.5) WeakRef
---
WeakRef provides two new pieces of functionality

creating weak references to objects with the WeakRef class
running user-defined finalizers after objects are garbage-collected, with the FinalizationRegistry class

```javascript
const myObject = new WeakRef({
  name: ‘Sudheer’,
  age: 34
});
console.log(myObject.deref()); //output: {name: “Sudheer”, age: 35}
console.log(myObject.deref().name); //output: Sudheer


// Create new FinalizationRegistry:
const reg = new FinalizationRegistry((val) => {
  console.log(val);
});

(() => {
// Create new object:
  const obj = {}

// Register finalizer for the "obj" as first argument and value for callback function as second argument:
  reg.register(obj, 'obj has been garbage-collected.')
})();
```


## ES2022-ES13
---

https://dev.to/brayanarrieta/new-javascript-features-ecmascript-2022-with-examples-4nhg

###### 8.1) Top-level await
---

```javascript
//The old behavior

await Promise.resolve(console.log('Hello World'));
// Output: SyntaxError: await is only valid in async function

// Alternative to fix the problem
(async function() {
  await Promise.resolve(console.log('Hello World'));
  // Output: Hello World
}());
```


```javascript
await Promise.resolve(console.log('Hello World'));
// → Hello World


//Dynamic dependency pathing
const strings = await import(`/i18n/${navigator.language}`);

//Resource initialization
const connection = await dbConnector();

// Dependency fallbacks
let jQuery;
try {
  jQuery = await import('https://cdn-a.com/jQuery');
} catch {
  jQuery = await import('https://cdn-b.com/jQuery');
}
```

###### 8.2) Private instance fields, methods, and accessors
---
Previously when was needed to declare a private method or field needs to be added an underscore at the beginning of the method name (based on convention), however, that does not guarantee that the method will be private.

With ES2022 was added as new features as private instance fields, methods, and accessors. We need to add just # at the beginning of the method name and in that way will be declared as private.

```javascript
class Test {
  #firstName = 'test-name';
}

const test = new Test();
test.firstName

// Output: undefined
```

```javascript
class Test {

  #addTestRunner(testRunner){
    this.testRunner = testRunner
  }
}

const test = new Test();
test.addTestRunner({name: 'test'});

// Output: TypeError: test.addTestRunner is not a function
```

```javascript
Private accessors (getters and setters)

class Test {

  get #name(){
    return 'test-name';
  }
}

const test = new Test();
test.name

// Output: undefined
```

###### 8.3) Static class fields and methods
---
Static class fields and methods are not used on instances of a class. Instead, can be called on the class itself and is declared using the static keyword

Static methods are often utility functions, and helpers, whereas static properties are useful for caches, fixed-configuration, or any other data we don’t need to be replicated across instances.

```javascript
class Test {
  static firstName = 'test-static-name';
}

Test.firstName

// Output: test-static-name


class Test {
  static greeting(){
    console.log('Hello this is a greeting from a static method');
  }
}

Test.greeting();

// Output: Hello this is a greeting from a static method
```

###### 8.4) Static class initialization blocks


###### 8.5) Error: .cause
Error and its subclasses now let us specify the reason behind the error.

With the Error cause, we can add more intrinsic information for our errors. To use this new feature, we should specify the error options as a second parameter, and with the cause key we can pass the error that we want to chain.

```javascript
const getUsers = async(array)=> {
  try {
    const users =  await fetch('https://myapi/myusersfake');
    return users;
  } catch (error) {
    console.log('enter')
    throw new Error('Something when wrong, please try again later', { cause: error })
  }
}

try{
  const users = await getUsers();
} catch(error) {
  console.log(error); // Error: The array need a minimum of two elements
  console.log(error.cause); // TypeError: Failed to fetch
}
```

###### 8.6) Array, String, and TypedArray: .at() Method


```javascript
const fruitsArray = ['banana', 'apple', 'orange', 'kiwi'];
console.log(fruitsArray[fruitsArray.length -1])
// Output: kiwi

const fruit = 'kiwi';
console.log(fruit[fruit.length -1])
// Output: i
```

```javascript
const fruitsArray = ['banana', 'apple', 'orange', 'kiwi'];
console.log(fruitsArray.at(-1))
// Output: kiwi

const fruit = 'kiwi';
console.log(fruit.at(-1))
// Output: i
```

###### 8.6) Object: .hasOwn()


```javascript
let hasOwnProperty = Object.prototype.hasOwnProperty

if (hasOwnProperty.call(object, "foo")) {
  console.log("has property foo")
}
```

```javascript
if (Object.hasOwn(object, "foo")) {
  console.log("has property foo")
}
```



###### 8.6) RegExp: match .indices ('d' flag)

The new /d flag feature provides some additional information about the start and indices position end of each match in the input string.

```javascript
const regexExample2022 = /greeting(\d)/dg;
const exampleString = 'greeting1greeting2';
const result = [...exampleString.matchAll(regexExample2022)];
console.log(result[0]);
```

