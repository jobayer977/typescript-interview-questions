# Frequently Asked JavaScript Interview Questions 
 ### Resources 
- [Interview-questions - by Toptal](https://www.toptal.com/javascript/interview-questions) 
- [Javascript-interview-questions - by sudheerj](https://github.com/sudheerj/javascript-interview-questions) 
- [javascript-questions - by lydiahallie](https://github.com/lydiahallie/javascript-questions) 
 

 ## Table of Contents

- [1 Difference between explicit and implicit types in typescript ?](#difference-between-explicit-and-implicit-types-in-typescript)
- [2 Do we need to compile TypeScript files and why?](#do-we-need-to-compile-typescript-files-and-why)
- [3 How to call base class constructor from child class in TypeScript?](#how-to-call-base-class-constructor-from-child-class-in-typescript)
- [4 List the built-in types in Typescript ?](#list-the-built-in-types-in-typescript)
- [5 What are the benefits of TypeScript?](#what-are-the-benefits-of-typescript)
- [6 What is interface in typescript?](#what-is-interface-in-typescript)
- [7 What is static type checking in TypeScript?](#what-is-static-type-checking-in-typescript)
- [8 What is Typescript?](#what-is-typescript)
- [9 What is Unions in typescript?](#what-is-unions-in-typescript)
- [10 Why is generic used in TypeScript?](#why-is-generic-used-in-typescript)
<br/><br/><br/><br/>

1. ### Difference between explicit and implicit types in typescript ?

Explicit types are used when you know the type of the variable. Implicit types are used when you don't know the type of the variable.

**Explicit types**

```typescript
let name: string = "John"
let age: number = 30
let isMarried: boolean = false
```

**Implicit types**

```typescript
let name = 'John'
let age = 30

let isMarried = false

```

2. ### Do we need to compile TypeScript files and why?

Yes we do. Typescript is just a language Extension browsers can't interpret it. Converting from TypeScript to JavaScript is called compiling. Compiling doesn't mean binary code is created in this case. For this kind of translation, also the term transpilation is used instead of compilation.

3. ### How to call base class constructor from child class in TypeScript?

We can call base class constructor using `super()`.

4. ### List the built-in types in Typescript ?

Number type: it is used to represent number type values and represents double precision floating point values.

```typescript
var variable_name: number;
```

**String type:** it represents a sequence of characters stored as Unicode UTF-16 code. It is the same as JavaScript primitive type.

```typescript
var variable_name: string;
```

**Boolean type:** in Typescript, it is used to represent a logical value. When we use the Boolean type, we get output only in true or false. It is also the same as JavaScript primitive type.

```typescript
variable_name
```

**Null type:** it represents a null literal and it is not possible to directly reference the null type value itself.

```typescript
var variable_name:number = null;

```

**Undefined type:** it is the type of undefined literal. This type of built-in type is the sub-type of all the types.

```typescript
var variable_name:number = undefined;

```

5. ### What are the benefits of TypeScript?

The main benefit of TypeScript is that it can highlight unexpected behavior in your code, lowering the chance of bugs.

- It helps in code structuring.
- Use class based object oriented programming.
- Impose coding guidelines.
- Offers type checking.
- Compile time error checking.
- Intellisense

6. ### What is interface in typescript?

Interface is a blueprint of an object which is used to define the properties and methods of an object. It is used to define the structure of an object. and helpfull in type checking.

You can explicitly describe this object’s shape using an interface declaration:

```typescript
interface Person {
 firstName: string
 lastName: string
}

var person: Person = {
 firstName: 'John',
 lastName: 'Doe',
}

```

7. ### What is static type checking in TypeScript?

It is a type system that is used to check the type of variables and functions at compile time. Used to prevent runtime errors and improve the readability of the code. Static type checking is helpful in debugging and also in writing clean and readable code and IDE intellisense features.

```typescript
const message = "hello!";
message()
//ERROR:  This expression is not callable.
```

8. ### What is Typescript?

TypeScript is a free and open-source programming language developed and maintained by Microsoft. It is a strict syntactical superset of JavaScript, and adds optional static typing and class-based object-oriented programming to the language.

9. ### What is Unions in typescript?

Unions are a way to combine multiple types into a single type.

**Variable Example**

```typescript
let isDone: boolean | number = false
```

**Function Example**

```typescript
function add(x: number, y: number): number | boolean {
 return x + y
}
```

10. ### Why is generic used in TypeScript?

Generics are able to create a component or function to work over a variety of types rather than a single one.

```typescript
/** A class definition with a generic parameter */
class Queue<T> {
  private data = [];
  push = (item: T) => this.data.push(item);
  pop = (): T => this.data.shift();
}

const queue = new Queue<number>();
queue.push(0);
queue.push("1"); // ERROR : cannot push a string. Only numbers allowed
```

