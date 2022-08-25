# Frequently Asked Typescript Interview Questions 
 ### Resources 
- [Typescript Documentations](https://www.typescriptlang.org/) 
- [Fullstack Cafe](https://www.fullstack.cafe) 
 

 ## Table of Contents

- [1 Difference between explicit and implicit types in typescript ?](#difference-between-explicit-and-implicit-types-in-typescript)
- [2 Why is generic used in TypeScript?](#why-is-generic-used-in-typescript)
- [3 What is build time error?](#what-is-build-time-error)
- [4 Differences Between Type Aliases and Interfaces?](#differences-between-type-aliases-and-interfaces)
- [5 Typescript make all properties readonly ?](#typescript-make-all-properties-readonly)
- [6 What does Required do in TypeScript?](#what-does-required-do-in-typescript)
- [7 what is enum in typescript](#what-is-enum-in-typescript)
- [8 What is literal type in typescript](#what-is-literal-type-in-typescript)
- [9 What is Pick type in TypeScript?](#what-is-pick-type-in-typescript)
- [10 What is the purpose of Record in typescript](#what-is-the-purpose-of-record-in-typescript)
- [11 What is type assertion?](#what-is-type-assertion)
- [12 Do we need to compile TypeScript files and why?](#do-we-need-to-compile-typescript-files-and-why)
- [13 What is type casting in typescript](#what-is-type-casting-in-typescript)
- [14 What is type guard in typescript](#what-is-type-guard-in-typescript)
- [15 what is type narrowing in typescript](#what-is-type-narrowing-in-typescript)
- [16 When should I use unknown keyword TypeScript?](#when-should-i-use-unknown-keyword-typescript)
- [17 What are Modules in Typescript?](#what-are-modules-in-typescript)
- [18 Why do we need to compile TypeScript?](#why-do-we-need-to-compile-typescript)
- [19 How do you call a constructor of parent class in child class?](#how-do-you-call-a-constructor-of-parent-class-in-child-class)
- [20 What is the difference between .ts and .tsx ?](#what-is-the-difference-between-ts-and-tsx)
- [21 What is the difference between interface and classes?](#what-is-the-difference-between-interface-and-classes)
- [22 How do you declare a class constant?](#how-do-you-declare-a-class-constant)
- [23 What does TypeScript map file do?](#what-does-typescript-map-file-do)
- [24 How to call base class constructor from child class in TypeScript?](#how-to-call-base-class-constructor-from-child-class-in-typescript)
- [25 What is getters setters in TypeScript?](#what-is-getters-setters-in-typescript)
- [26 What are conditional types in TypeScript?](#what-are-conditional-types-in-typescript)
- [27 How do you make an array read-only?](#how-do-you-make-an-array-read-only)
- [28 What is public and private in TypeScript?](#what-is-public-and-private-in-typescript)
- [29 What is override in TypeScript?](#what-is-override-in-typescript)
- [30 Does TypeScript have overloading?](#does-typescript-have-overloading)
- [31 Why do we use abstract class in TypeScript?](#why-do-we-use-abstract-class-in-typescript)
- [32 What is the declare keyword in TypeScript?](#what-is-the-declare-keyword-in-typescript)
- [33 What are decorators in TypeScript?](#what-are-decorators-in-typescript)
- [34 Should I use type or interface TypeScript?](#should-i-use-type-or-interface-typescript)
- [35 List the built-in types in Typescript ?](#list-the-built-in-types-in-typescript)
- [36 How do I combine two TypeScript interfaces?](#how-do-i-combine-two-typescript-interfaces)
- [37 What are the benefits of TypeScript?](#what-are-the-benefits-of-typescript)
- [38 What is interface in typescript?](#what-is-interface-in-typescript)
- [39 What is static type checking in TypeScript?](#what-is-static-type-checking-in-typescript)
- [40 What is Typescript?](#what-is-typescript)
- [41 What is Unions in typescript?](#what-is-unions-in-typescript)
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

2. ### Why is generic used in TypeScript?

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

3. ### What is build time error?

Errors that occur when you violate the rules of writing syntax are known as build-Time errors. This compiler error indicates something that must be fixed before the code can be compiled. All these errors are detected by the compiler and thus are known as build-time or compile-time errors.

4. ### Differences Between Type Aliases and Interfaces?
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

5. ### Typescript make all properties readonly ?

Constructs a type with all properties of Type set to readonly, meaning the properties of the constructed type cannot be reassigned.

```typescript
interface Todo {
  title: string;
}
 
const todo: Readonly<Todo> = {
  title: "Delete inactive users",
};
 
todo.title = "Hello";
// Cannot assign to 'title' because it is a read-only property.
```

6. ### What does Required do in TypeScript?

Constructs a type consisting of all properties of Type set to required. The opposite of Partial.

```typescript
interface Props {
  a?: number;
  b?: string;
}
 
const obj: Props = { a: 5 };
 
const obj2: Required<Props> = { a: 5 };

//Property 'b' is missing in type '{ a: number; }' but required in type 'Required<Props>'.
```

7. ### what is enum in typescript
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

8. ### What is literal type in typescript
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

9. ### What is Pick type in TypeScript?
Constructs a type by picking the set of properties Keys (string literal or union of string literals) from Type.

```typescript
interface Todo {
  title: string;
  description: string;
  completed: boolean;
}
type TodoPreview = Pick<Todo, "title" | "completed">;
const todo: TodoPreview = {
  title: "Clean room",
  completed: false,
  description:'ddd' // Type '{ title: string; completed: false; description: string; }' is not assignable to type 'Pick<Todo, "title" | "completed">'.
};
```

10. ### What is the purpose of Record in typescript

Constructs an object type whose property keys are Keys and whose property values are Type. This utility can be used to map the properties of a type to another type.

```typescript
interface CatInfo {
  age: number;
  breed: string;
}
 
type CatName = "miffy" | "boris" | "mordred";
 
const cats: Record<CatName, CatInfo> = {
  miffy: { age: 10, breed: "Persian" },
  boris: { age: 5, breed: "Maine Coon" },
  mordred: { age: 16, breed: "British Shorthair" },
};
 
cats.boris // const cats: Record<CatName, CatInfo>
```

11. ### What is type assertion?

 Type assertions enable you to override default type inference for neutral types. Type assertion is a technique that informs the compiler about the type of a variable. Type assertion is similar to typecasting but it doesn’t reconstruct code. You can use type assertion to specify a value’s type and tell the compiler not to deduce it. When we want to change a variable from one type to another such as any to number etc, we use Type assertion.

**Example**

```typescript

let str: unknown = "Typescript";
console.log(str);
  
let len: number = (str as string).length;
console.log(len);             
                        
```

12. ### Do we need to compile TypeScript files and why?

Yes we do. Typescript is just a language Extension browsers can't interpret it. Converting from TypeScript to JavaScript is called compiling. Compiling doesn't mean binary code is created in this case. For this kind of translation, also the term transpilation is used instead of compilation.

13. ### What is type casting in typescript

Type casting means changing an expression from one data type to another.

TypeScript is compiled to JavaScript and behaves differently; it does not give two hoots about the types defined by you, and there is no runtime to enforce types during the execution.

Example

```typescript

let data: string = '123';
console.log("Type of Data before Type Cast==>", typeof data);
console.log("Type of Data after Type Cast==>", typeof Number(data));

```

14. ### What is type guard in typescript


A type guard is a TypeScript technique used to get information about the type of a variable, usually within a conditional block. Type guards are regular functions that return a boolean, taking a type and telling TypeScript if it can be narrowed down to something more specific.

**Example**

```typescript

function StudentId(x: string | number) {
    if (typeof x == 'string') {
        console.log('Student');
    }
    if (typeof x === 'number') {
        console.log('Id');
    }
}
StudentId(`446`); //prints Student
StudentId(446); //prints Id

```

15. ### what is type narrowing in typescript

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

16. ### When should I use unknown keyword TypeScript?
We may need to describe the type of variables that we do not know when we are writing an application. These values may come from dynamic content – e.g. from the user – or we may want to intentionally accept all values in our API. In these cases, we want to provide a type that tells the compiler and future readers that this variable could be anything, so we give it the unknown type.

```typescript
let notSure: unknown = 4;
notSure = "maybe a string instead";
 
// OK, definitely a boolean
notSure = false;
```

17. ### What are Modules in Typescript?

In Typescript, we can use modules to organize our code. A module is a file that contains a group of related code. We can make some of them public to view from outside the module, and some of them private to hide from outside the module. To make a module public, we use the export keyword.

### Example

**index.ts**

```typescript
export class Person {
	name: string = ''
	constructor(public name: string) {
		this.name = name
	}
}
```

**App.ts**

```typescript
import { Person } from './index'

const person = new Person('John Doe')

console.log(person.name)
```

18. ### Why do we need to compile TypeScript?

Browser can only understand JavaScript. So we need to compile Typescript to JavaScript. If we try to run Typescript code directly, it will not work. Because browsers don't understand it.

19. ### How do you call a constructor of parent class in child class?

To call a constructor of parent class in child class, we use `super` keyword.

**Example:**

```typescript
class Person {
	name: string = ''
	constructor(public name: string) {
		this.name = name
	}
}

class Employee extends Person {
	constructor(public name: string) {
		super(name)
	}
}

const employee = new Employee('John Doe')
console.log(employee.name)
```

20. ### What is the difference between .ts and .tsx ?

`.ts` files contains only pure TypeScript
`.tsx` have included JSX also.

On another point of view, you can copy everything from a .ts file and paste on .tsx file, and you don't need to modify anything. But if you're copying from a .tsx file you need to refactor it by removing the JSX elements.

21. ### What is the difference between interface and classes?

A class is a blueprint from which we can create objects that share the same configuration - properties and methods. An interface is a group of related properties and methods that describe an object, but don't specify how they are implemented.

**Example of class:**

```typescript
class Person {
	name: string = ''
	constructor(public name: string) {
		this.name = name
	}
}

const person = new Person('John Doe')
console.log(person.name)
```

**Example of interface:**

```typescript
interface Person {
	name: string
}

const person: Person = {
	name: 'John Doe',
}
console.log(person.name)
```

22. ### How do you declare a class constant?

Typescript allows you to declare a constant inside a class. But we can use the readonly keyword to declare a constant. It is a constant that is shared by all instances of a class. But it is not modifiable.

**Example:**

```typescript
class Person {
	readonly name: string = ''
	constructor(public name: string) {
		this.name = name
	}
}

const person = new Person('John Doe')
console.log(person.name)

person.name = 'Jane Doe' // Error: Cannot assign to 'name' because it is a constant or a read-only property.
```

23. ### What does TypeScript map file do?

`.map` files are source map files that let tools map between the emitted JavaScript code and the TypeScript source files that created it. Many debuggers (e.g. Visual Studio or Chrome's dev tools) can consume these files so you can debug the TypeScript file instead of the JavaScript file.

24. ### How to call base class constructor from child class in TypeScript?

We can call base class constructor using `super()`.

25. ### What is getters setters in TypeScript?

TypeScript has getters and setters. Getters and setters as a way of intercepting and modifying the value of a property. This gives us the ability to do things like enforce data types, or to make sure that a property is never null.

**Example**

```typescript
class Employee {
    private _fullName: string;

    get fullName(): string {
        return this._fullName;
    }
    set fullName(newName: string) {
        this._fullName = newName;
    }
}

let employee = new Employee();
employee.fullName = "Bob Smith";
employee.fullName; // "Bob Smith"
```

26. ### What are conditional types in TypeScript?

Taking a decision makes function useful for a different type of input. Conditional types, as the name suggests, define the types of value on the basis of conditions. Now, Conditional types seem like a conditional statement, although, it is same in the way that the conditional statement is used to choose the flow of code based on certain conditions and conditional  types used for choosing different types for values.

27. ### How do you make an array read-only?
Using the typescript utility. The `ReadonlyArray<T>` type is a read-only array type. It is a subtype of the `Array<T>` type. This type is useful when you want to ensure that the array is read-only.

**Example**

```typescript
const arr: ReadonlyArray<number> = [1, 2, 3];
arr[0] = 4; // Error!
arr.push(4); // Error!
arr.length = 0; // Error!
arr.splice(0, 1); // Error!
```

28. ### What is public and private in TypeScript?

Typescript provide us three access modifiers: public, private and protected.

**Public**
The public access modifier is used to declare a property or method as public. It is the default access modifier.

```typescript
class Employee {
    public name: string;
    public getName(): string {
        return this.name;
    }
}
const emp = new Employee();
emp.name = 'John'; 
console.log(emp.getName()); // John
```

**Private**
The private access modifier is used to declare a property or method as private. It is used to hide the property or method from outside the class.

```typescript
class Employee {
    private name: string;
    private getName(): string {
        return this.name;
    }
}
const emp = new Employee();
emp.name = 'John';
console.log(emp.getName()); // Error: Property 'getName' is private and only accessible within class 'Employee'.
```

**Protected**
The protected access modifier is used to declare a property or method as protected. It is used to hide the property or method from outside the class and its subclasses.

```typescript
class Employee {
    protected name: string;
    protected getName(): string {
        return this.name;
    }
}
class Manager extends Employee {
    constructor() {
        super();
        this.name = 'John';
    }
    getName(): string {
        return super.getName();
    }
}
const emp = new Employee();
emp.name = 'John';
console.log(emp.getName()); // Error: Property 'getName' is protected and only accessible within class 'Employee' and its subclasses.
const mgr = new Manager();
console.log(mgr.getName()); // John
```

**Difference between private and protected**
Private access modifier is used to hide the property or method from outside the class. Protected access modifier is used to hide the property or method from outside the class and its subclasses.

29. ### What is override in TypeScript?

Method Overriding is a process of overthrowing a method of super class by method of same name and parameters in sub class. Method Overriding is useful when sub class wants to modify the behavior of super class for certain tasks.

**Example WithOut Overriding**

```typescript
class Base {
 public name: string = ''
 public getName(): string {
  return `${this.name} Base`
 }
}
class Sub extends Base {
 constructor() {
  super()
  this.name = 'John'
 }
}

const sub = new Sub()
console.log(sub.getName()) // John Base
```

**Example With Overriding**

```typescript
class Base {
 public name: string = ''
 public getName(): string {
  return `${this.name} Base`
 }
}
class Sub extends Base {
 constructor() {
  super()
  this.name = 'John'
 }
 public getName(): string {
  return `${this.name} Sub`
 }
}

const sub = new Sub()
console.log(sub.getName()) // John Sub
```

30. ### Does TypeScript have overloading?

TypeScript provides the concept of function overloading. You can have multiple functions with the same name but different parameter types and return type. However, the number of parameters should be the same.

```typescript
function add(a: number, b: number): number;
function add(a: string, b: string): string;
function add(a: number, b: string): string;

function add(a: any, b: any): any {
  return a + b;
}

add(1, 2); // 3

add("1", "2"); // "12"

add(1, "2"); // "12"
```

31. ### Why do we use abstract class in TypeScript?

Abstract classes are base classes from which other classes may be derived. They may not be instantiated directly. Unlike an interface, an abstract class may contain implementation details for its members. The abstract keyword is used to define abstract classes as well as abstract methods within an abstract class.

```ts
abstract class Animal {
    abstract makeSound(): void;
    move(): void {
        console.log('roaming the earth...');
    }
}
 

class Dog extends Animal {
    makeSound(): void {
        console.log('woof');
    }
}
```

32. ### What is the declare keyword in TypeScript?
The declare keyword in TypeScript is used for declaring a variable or a function as a type. It is used for declaring a variable or a function as a type.

## Example

```typescript
declare var x: number;
declare function add(x: number, y: number): number;
```

33. ### What are decorators in TypeScript?
A Decorator is a special kind of declaration that can be attached to a class declaration, method, accessor, property, or parameter. Decorators use the form @expression , where expression must evaluate to a function that will be called at runtime with information about the decorated declaration.

34. ### Should I use type or interface TypeScript?
nterfaces are most recommended for defining new objects or methods or properties of an object where it will receive a specific component. Hence interface works better when using objects and method objects. Therefore it is our choice to choose between types or interface according to the program needs.

35. ### List the built-in types in Typescript ?

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

36. ### How do I combine two TypeScript interfaces?

To merge two interfaces with TypeScript, we can use extends to extend multiple interfaces. to create the IFooBar that extends IFoo and IBar . This means IFooBar has all the members from both interfaces inside.

**Example**

```typescript
interface IFoo {
    foo(): void;
}
interface IBar {
    bar(): void;
}

interface IFooBar extends IFoo, IBar {
}
```

37. ### What are the benefits of TypeScript?

The main benefit of TypeScript is that it can highlight unexpected behavior in your code, lowering the chance of bugs.

- It helps in code structuring.
- Use class based object oriented programming.
- Impose coding guidelines.
- Offers type checking.
- Compile time error checking.
- Intellisense

38. ### What is interface in typescript?

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

39. ### What is static type checking in TypeScript?

It is a type system that is used to check the type of variables and functions at compile time. Used to prevent runtime errors and improve the readability of the code. Static type checking is helpful in debugging and also in writing clean and readable code and IDE intellisense features.

```typescript
const message = "hello!";
message()
//ERROR:  This expression is not callable.
```

40. ### What is Typescript?

TypeScript is a free and open-source programming language developed and maintained by Microsoft. It is a strict syntactical superset of JavaScript, and adds optional static typing and class-based object-oriented programming to the language.

41. ### What is Unions in typescript?

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

