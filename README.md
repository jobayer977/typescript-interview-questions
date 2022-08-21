# Frequently Asked JavaScript Interview Questions 
 ### Resources 
- [Typescript Documentations](https://www.typescriptlang.org/) 
 

 ## Table of Contents

- [1 Differences Between Type Aliases and Interfaces?](#differences-between-type-aliases-and-interfaces)
- [2 Difference between explicit and implicit types in typescript ?](#difference-between-explicit-and-implicit-types-in-typescript)
- [3 Do we need to compile TypeScript files and why?](#do-we-need-to-compile-typescript-files-and-why)
- [4 How to call base class constructor from child class in TypeScript?](#how-to-call-base-class-constructor-from-child-class-in-typescript)
- [5 List the built-in types in Typescript ?](#list-the-built-in-types-in-typescript)
- [6 What are the benefits of TypeScript?](#what-are-the-benefits-of-typescript)
- [7 What is build time error?](#what-is-build-time-error)
- [8 what is enum in typescript](#what-is-enum-in-typescript)
- [9 What is interface in typescript?](#what-is-interface-in-typescript)
- [10 What is literal type in typescript](#what-is-literal-type-in-typescript)
- [11 What is static type checking in TypeScript?](#what-is-static-type-checking-in-typescript)
- [12 What is type assertion?](#what-is-type-assertion)
- [13 What is type casting in typescript](#what-is-type-casting-in-typescript)
- [14 what is type narrowing in typescript](#what-is-type-narrowing-in-typescript)
- [15 What is Typescript?](#what-is-typescript)
- [16 What is Unions in typescript?](#what-is-unions-in-typescript)
- [17 Why is generic used in TypeScript?](#why-is-generic-used-in-typescript)
<br/><br/><br/><br/>

1. ### Differences Between Type Aliases and Interfaces?
Type aliases and interfaces are similar but not the same. The key difference is that interfaces are extensible whereas type aliases are not. Type aliases are used to create a new type that is a subset of an existing type. Interfaces are used to create a new type that is a superset of an existing type.

**Extending an interface**

```typescript
interface Animal {
  name: string
}

interface Bear extends Animal {
  honey: boolean
}

const bear = getBear() 
bear.name
bear.honey
        
```

**Extending a type via intersections**

```typescript
type Animal = {
  name: string
}

type Bear = Animal & { 
  honey: boolean 
}

const bear = getBear();
bear.name;
bear.honey;
        
```

2. ### Difference between explicit and implicit types in typescript ?

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

3. ### Do we need to compile TypeScript files and why?

Yes we do. Typescript is just a language Extension browsers can't interpret it. Converting from TypeScript to JavaScript is called compiling. Compiling doesn't mean binary code is created in this case. For this kind of translation, also the term transpilation is used instead of compilation.

4. ### How to call base class constructor from child class in TypeScript?

We can call base class constructor using `super()`.

5. ### List the built-in types in Typescript ?

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

6. ### What are the benefits of TypeScript?

The main benefit of TypeScript is that it can highlight unexpected behavior in your code, lowering the chance of bugs.

- It helps in code structuring.
- Use class based object oriented programming.
- Impose coding guidelines.
- Offers type checking.
- Compile time error checking.
- Intellisense

7. ### What is build time error?

Errors that occur when you violate the rules of writing syntax are known as build-Time errors. This compiler error indicates something that must be fixed before the code can be compiled. All these errors are detected by the compiler and thus are known as build-time or compile-time errors.

8. ### what is enum in typescript
In TypeScript, enums, or enumerated types, are data structures of constant length that hold a set of constant values. Each of these constant values is known as a member of the enum. Enums are useful when setting properties or values that can only be a certain number of possible values.

```typescript
enum UserResponse {
  No = 0,
  Yes = 1,
}

function respond(recipient: string, message: UserResponse): void {
  console.log(recipient, message); // "Princess Caroline",  1
}

respond("Princess Caroline", UserResponse.Yes);

```

9. ### What is interface in typescript?

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

10. ### What is literal type in typescript
TypeScript Literal Types restrict the value of a variable to finite valid values. This is in contrast to the variable which allows you to change value (except for TypeScript Constants). The latest version of Typescript supports the String Literal Types, Numeric Literal Types, Boolean Literal Types & Enum Literal Types.

**Example**

```typescript
type Easing = "ease-in" | "ease-out" | "ease-in-out";
```

```typescript
interface ValidationSuccess {
  isValid: true;
  reason: null;
}
interface ValidationFailure {
  isValid: false;
  reason: string;
}
type ValidationResult = ValidationSuccess | ValidationFailure;
```

11. ### What is static type checking in TypeScript?

It is a type system that is used to check the type of variables and functions at compile time. Used to prevent runtime errors and improve the readability of the code. Static type checking is helpful in debugging and also in writing clean and readable code and IDE intellisense features.

```typescript
const message = "hello!";
message()
//ERROR:  This expression is not callable.
```

12. ### What is type assertion?

 Type assertions enable you to override default type inference for neutral types. Type assertion is a technique that informs the compiler about the type of a variable. Type assertion is similar to typecasting but it doesn’t reconstruct code. You can use type assertion to specify a value’s type and tell the compiler not to deduce it. When we want to change a variable from one type to another such as any to number etc, we use Type assertion.

**Example**

```typescript

let str: unknown = "Typescript";
console.log(str);
  
let len: number = (str as string).length;
console.log(len);             
                        
```

13. ### What is type casting in typescript

Type casting means changing an expression from one data type to another.

TypeScript is compiled to JavaScript and behaves differently; it does not give two hoots about the types defined by you, and there is no runtime to enforce types during the execution.

Example

```typescript

let data: string = '123';
console.log("Type of Data before Type Cast==>", typeof data);
console.log("Type of Data after Type Cast==>", typeof Number(data));

```

14. ### what is type narrowing in typescript

Type narrowing is just what it sounds like—narrowing down a general type into something more precise. If you've ever dealt with union types, e.g. string | number you've certainly encountered this. In fact, optional types such as x?: number often require narrowing as well, as this typing is equivalent to x: number | undefined. In both of these cases, you'll likely need to handle each case in your code, and for that you'll need to narrow down the type first.

**Ways to Narrow These Types**
To narrow a union type down to one, we'll need to consider each case. We can do this with good old-fashioned control flow in JavaScript, as the TypeScript compiler is clever enough to infer the narrowing from our conditional logic. Typically, this just means using if or switch statements.

Let's consider a common, real-world example that I'm sure you've all written once or twice: a function that returns the deliciousness score for a given type of candy.

```typescript
type Candy =
  | { name: "Skittles"; type: "Regular" | "Tropical" }
  | { name: "Black Licorice"; qty: number }
  | { name: "Runts"; isBanana: boolean };

function rateCandy(candy: Candy): number {
  switch (candy.name) {
    case "Skittles":
      return candy.type === "Regular" ? 8 : 7;
    case "Black Licorice":
      return candy.qty * -1;
    case "Runts":
      return candy.isBanana ? 11 : 5;
    default:
      throw new Error(`"${candy}" is not a valid candy!`);
  }
}
```

15. ### What is Typescript?

TypeScript is a free and open-source programming language developed and maintained by Microsoft. It is a strict syntactical superset of JavaScript, and adds optional static typing and class-based object-oriented programming to the language.

16. ### What is Unions in typescript?

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

17. ### Why is generic used in TypeScript?

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

