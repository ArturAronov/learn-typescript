# Learn TypeScript
### Notes
- ``tsc filename.ts`` -> compiles the .ts file into .js
- core types:
  - ``string``
  - ``number``
  - ``boolean``
  - ``object``
  - array: ``string[]`` / ``number[]`` / ``boolean[]`` / ``any[]``
- special types:
  - Tuple -> an array of fixed length and type (see [code example 2](#2-tuple))
  - Enum -> ``{ADMIN, USER}`` (see [code example 3](#3-enum))
- when declaring a ``let`` variable without value assigned to it, it is advised to add type to it, such as ``let num: number;``. However this is not a good practice when a value to the variable is assigned explicitly (such as ``const num: number = 1``), as the type gets already passed in the function parameter.

### Code Examples
#### 1 Basics
```
function add(n1: number, n2: number) {
  return n1 + n2;
};

const result = add(5 + 2.8)
```
- n1: number & n2: number -> params with type of number

#### 2 Tuple
```
const employee: [number, string] = [1, "Steve"];
```
*or*
```
let user: [number, string, boolean, number, string];  // declare tuple variable
user = [1, "Steve", true, 20, "Admin"];               // initialize tuple variable
```
**nested Tuple array**
```
let employee: [number, string][];
employee = [[1, "Steve"], [2, "Bill"], [3, "Jeff"]];
```
**adding elements into Tuple**
```
let employee: [number, string] = [1, "Steve"];
employee.push(2, "Bill");
console.log(employee); //Output: [1, 'Steve', 2, 'Bill']
```

#### 3 Enum
```
enum Role { ADMIN, READ_ONLY_USER, AUTHOR };

const person = {
  role: Role.READ_ONLY_USER
}

console.log(person.role)    //returns 1
```
*or*
```
enum Role { ADMIN, READ_ONLY_USER = 5, AUTHOR };

const person = {
  role: Role.READ_ONLY_USER
}

console.log(person.role)    //returns 5
```
*or*
```
enum Role { ADMIN, READ_ONLY_USER = 'read-only-user', AUTHOR };

const person = {
  role: Role.READ_ONLY_USER
}

console.log(person.role)    //returns 'read-only-user'
```
