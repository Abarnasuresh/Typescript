## Typescript         
* Typescript is an open source language developed and maintained by the microsoft
* Typescript is the superset of the javascript
* Adding new features and advantages to javascript
* Browsers cant execute the typescript
* Typescript code compiled to javascript code
* TypeScript is a programming language but also it is a tool.
* TypeScript helps to prevent some errors during development
### Key Difference: 
There are one key different between TypeScript and JavaScript is
* JavaScript uses ‘dynamic type’(resolved at runtime)
* TypeScript uses ‘static type’(set during development).
### CORE TYPES: 
Typescript enables us to write our own types which javascript already knows and ts all the supports.
One of the core type we work with bot ts and js is Number.
### NUMBER: 
* There is no special type for integers,floats ,numbers with or without decimal are all considered as Number type.
* Other programming languages have special integer type,float type but both js and ts doesn’t have it. 
### STRING:
* String datatype that would be a text with the 'Hi',"Hi",`Hi`
* Strings are simply a text and javascript knows about the string value types
### BOOLEAN:
* Boolean datatype is an true,false working with if statements just these two,no "truthy" or "falsy"
values.
## Type of Inference:
TypeScript knows the JavaScript language and  it will generate types for you in many cases.
For example: in creating a variable and assigning it to a particular value, TypeScript will use the value as its type.
```javascript
let helloworld="hello world"
    let helloworld:string
```
* TypeScript knows that helloWorld is a string
* TypeScript can build a type-system that accepts JavaScript code but has types. 
# OBJECT
* The fundamental way that we group and pass around data is through objects. In TypeScript, we represent those through object types
```js
function greet(person: { name: string; age: number }) {
  return "Hello " + person.name;
}
```
## ARRAY TYPE
* A TypeScript array is an ordered list of data. To declare an array that holds values of a specific type, we use syntax:
ts
let skill = skills[0];
console.log(typeof(skill));

Array properties and methods
* TypeScript arrays can access the properties and methods of a JavaScript. For example,  the length property to get the number of element in an array
```js
let series = [1, 2, 3];
console.log(series.length); // 3
```
## Tuples
* Array consists of values of homogeneous (same) types but sometimes when we need to store a collection of a different types values in a single variable, then we will go with Tuples.
```js
Syntax:
let tuple_name = [val1, val2, val3, ...val n];  
```
Example:
```
let arrTuple = [501, "welcome", 505, "Mohan"];  
console.log(arrTuple);
```
## Enums
* Enums are one of the few features TypeScript has which is not a type-level extension of JavaScript.
* Enums allow a developer to define a set of named constants. 
* Using enums can make it easier to document intent, or create a set of distinct cases. TypeScript provides both numeric and string-based enums.
Numeric enum
```js
enum Direction {
  Up = 1,
  Down,
  Left,
  Right,
}
```
String enum
* In a string enum, each member has to be constant-initialized with a string literal, or with another string enum member.
ts
enum Direction {
  Up = "UP",
  Down = "DOWN",
  Left = "LEFT",
  Right = "RIGHT",
}
### The any Type:
TypeScript any type allows you to store a value of any type.
##### Why we use any  in TypeScript:
Special type any is used to tell TypeScript that a variable can be of any type.
### Union Type:
* Typescript a union type variable is a variable in which can store multiple type of values(i.e. number,string etc)
* Variables are defined using the pipe ( '|' ) symbol between the types. 
```js
let myVar: string | number; //myVar can store string and number types
```
### Literal Types:
There are three sets of literal types available in TypeScript today
* strings 
* numbers
* booleans
By using literal types you can allow an exact value which a string, number, or boolean must have.
### Literal Narrowing:
When you declare a variable via var or let, you are telling the compiler that there is the chance that this variable will change its contents.
### String Literal Types:
In practice string literal types combine nicely with union types, type guards, and type aliases.
### Numeric Literal Types:
TypeScript also has numeric literal types, which act the same as the string literals
### Boolean Literal Types:
Typescript also has boolean literal types you might use these to constrain object values whose properties ar interrelated.
<!-- ### Function Type and call backs:
A callback function is defined as a function passed into another function as an argument -->
## Type aliases
* We’ve been using object types and union types by writing them directly in type annotations. 
* This is convenient, but it’s common to want to use the same type more than once and refer to it by a single name.
```javascript
type Point = {
  x: number;
  y: number;
};
 
// Exactly the same as the earlier example
function printCoord(pt: Point) {
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}
 
printCoord({ x: 100, y: 100 });
```
## Function return types and void 
* The simplest way to describe a function is with a function type expression. These types are syntactically similar to arrow functions:
```javascript
function greeter(fn: (a: string) => void) {
  fn("Hello, World");
}
function printToConsole(s: string) {
  console.log(s);
}
greeter(printToConsole
```
## Return type void
* The void return type for functions can produce some unusual, but expected behavior.
```javascript
type voidFunc = () => void;
 
const f1: voidFunc = () => {
  return true;
};
 
const f2: voidFunc = () => true;
 
const f3: voidFunc = function () {
  return true;
};
```
## Callbacks
* A callback function is defined as a function passed into another function as an argument, which is then invoked inside the outer function to complete the desirable routine or action.
ts
function outerFunction(callback: () => void) {
  callback();
}

## The Unknown Type
* any and unknown are the same in terms of what is assignable to them, different in that unknown is not assignable to anything except any.
* Just like all types are assignable to any, all types are assignable to unknown. 
* This makes unknown another top type of TypeScript's type system (the other one being any).
```javascript
let value: unknown;
value = true; // OK
value = 42; // OK
value = "Hello World"; // OK
value = []; // OK
value = {}; // OK
value = Math.random; // OK
value = null; // OK
value = undefined;
value = new TypeError(); 
value = Symbol("type"); 
```
## The never Type
* When narrowing, you can reduce the options of a union to a point where you have removed all possibilities and have nothing left. 
* In those cases, TypeScript will use a never type to represent a state which shouldn’t exist.
* The never type is assignable to every type; however, no type is assignable to never (except never itself). 
* This means you can use narrowing and rely on never turning up to do exhaustive checking in a switch statement.

ts
type Shape = Circle | Square;
function getArea(shape: Shape) {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2;
    case "square":
      return shape.sideLength ** 2;
    default:
      const _exhaustiveCheck: never = shape;
      return _exhaustiveCheck;
  }
### Include and Exclude Files:
The "include" property allows you to include a list of TypeScript files using the glob wildcards pattern. The "exclude" property allows you to exclude a list of TypeScript files using the glob wildcards pattern.
```javascript
"include": ["node_modules/dashboard/**/*.ts"],
  "exclude": ["node_modules/dashboard/**/*.spec.ts"],
```
### Setting a Compilation Target:
TypeScript supports compiling a whole project at once by including the tsconfig. json file in the root directory.
### Source maps in typescript:
* Source maps enable us to debug TypeScript code. 
* A source map file maps from the transpiled JavaScript file to the original TypeScript file. 
```javascript
{
  "compilerOptions": {
    ...
    "sourceMap": true
  },
  ...
}
```
### Rootdir and Outdir:
* rootDir is the path to the folder with the source code of the app 
* OutDir is the path to the folder with compiled JavaScript files that will be executed by Node or Web browser 
### noemit on Error:
The noEmit option tells TypeScript that we only want to run type checking and do not want the compiler to output any transpiled code.
```javascript
const getAPI = async (url: string) => {
  // Get API
  return {};
};
```
### Debugging with Visual Studio Code:
TypeScript debugging supports JavaScript source maps. To generate source maps for your TypeScript files, compile with the --sourcemap option or set the sourceMap property in the tsconfig.json file to true.