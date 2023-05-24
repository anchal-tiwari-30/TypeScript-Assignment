Theory -<br>

Question 1: What are the basic data types in TypeScript?
---
Answer : Data types in TypeScript are -<br>
>`number`: It is used to represent both Integer as well as Floating-Point numbers.<br>
**const myNum: number = 1207;**

>`string`: Represents textual data.<br>
**let myString: string = 'abcd';**

>`boolean`: Represents the logical values true and false.
<br>
**const myBool: boolean = false;**

>`Null`: It is used when an object does not have any value<br>
**let a: null = null;**

>`Undefined`: Denotes value given to uninitialized variable<br>
**let b: undefined = undefined;**

>`Array` : Arrays in TypeScript are, like other data types, just like arrays in JavaScript.  Variables of data type array are declared two separate ways :<br>
**const myArr: number[] = [12, 90, 71];**
If the data types inside the array are unknown or a mixture of data types, the array can be declared using the `any` type:<br>
**const myArr: Array<any> = [12, 'three', false];**

>`Tuples` : This data type is best used when you know exactly how many variables you should have.  It is possible to reassign the value of the indices but not the amount of elements in the tuple.<br>
**let mine: [number, string];**

>`Enum` : more user friendly approach to giving names to numeric values.<br>
**enum Foods {'bacon', 'tomato', 'lettuce'};**

---
Question 2: What is Generic data type.
---
>Answer : A generic data type allows you to create reusable code components that can work with multiple types. It enables you to define placeholders (type parameters) within functions, classes, or interfaces, which can be replaced with specific types when the code is used.
Generics provide type safety and flexibility, as they allow you to create more generic and reusable functions and classes.
***

Question 3: What is type inferring in TS.
---
>Answer : TypeScript has a type inference mechanism that allows the compiler to automatically determine the type of a variable or expression based on its value and how it is used in the code. Type inference helps reduce the need for explicit type annotations, making code more concise and maintainable.
***
Question 4: What are the possible ways to define typing for functions.<br>
---
>Answer : Possible ways to define typing for functions:<br>
1.Method signatures<br>
2.Function type literals<br>
3.Object type literals with call/construct signatures
***
Question 5: How to define Generic type for Classes.<br>
---
>Answer : To define a generic type for a class, you can use angle brackets (<>) followed by one or more type parameters after the class name. For example, class MyClass<T> { ... }.
The type parameter T can then be used as a placeholder for a specific type within the class definition, allowing for flexibility and reusability.<br>
You can specify the generic type when creating an instance of the class, such as const instance = new MyClass`<number>`();, where number is the specific type argument provided for the generic type parameter T.
***
---
**Program -**<br>
--- 
**code** <br> 
```
var todos = [];
function add(name, description) {
 return todos.push({
 name: name,
 description: description,
 done: false
 });
}
function remove(index) {
 return todos.splice(index, 1);
}
function list() {
 todos.forEach(function(todo, index) {
 console.log(index + " - " + todo.name);
 });
}
function update(index, name, description) {
 todos[index].name = name;
 todos[index].description = description;
 return todos[index];
}
```
**Answer :** 
```
interface Todo { 
  name: string; 
  description: string;
  done: boolean;
}

var todos: Todo[] = [];

function add(name: string, description: string): number {
  return todos.push({
    name: name,
    description: description,
    done: false
  });
}

function remove(index: number): Todo[] {
  return todos.splice(index, 1);
}

function list(): void {
  todos.forEach(function(todo: Todo, index: number) {
    console.log(index + " - " + todo.name);
  });
}

function update(index: number, name: string, description: string): Todo {
  todos[index].name = name;
  todos[index].description = description;
  return todos[index];
} 