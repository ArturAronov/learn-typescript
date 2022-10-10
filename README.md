# Learn TypeScript
### Notes
- ``tsc filename.ts`` -> compiles the .ts file into .js
- types:
  - ``string``
  - ``number``
  - ``boolean``


### Code Examples
```
function add(n1: number, n2: number) {
  return n1 + n2;
};

const result = add(5 + 2.8)
```
  - n1: number & n2: number -> params with type of number
