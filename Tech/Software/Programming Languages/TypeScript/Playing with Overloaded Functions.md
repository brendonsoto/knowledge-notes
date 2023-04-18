---
aliases: 
created: 2023-01-06, 10:48:54 am (Friday, January 6th)
updated: 2023-01-06, 10:49:14 am (Friday, January 6th)
---
```typescript
/ Playing with Function Overloads
function f(x: string): string;
function f(x: number): string;
function f(x: string | number) {
  return x.toString();
}

console.log(f('12'))
console.log(f(12))

// Overloads where the result is slightly different
function g(x: string): { result: string };
function g(x: number): { result: number };
function g(x: string | number) {
  return {
    result: x
  }
}

g('12')
g(12)

// Similar but resulting obj has different properties
function h(x: string): { a: string };
function h(x: number): { b: number };
function h(x: string | number) {
  return typeof x === 'string'
    ? { a: 'a' }
    : { b: 1 };
}

let a = h('12')
let b = h(12)

// Testing with string literal values
function i(x: 'a'): { a: string };
function i(x: 'b'): { b: number };
function i(x: 'a' | 'b') {
  return typeof x === 'string'
    ? { a: 'a' }
    : { b: 1 };
}

let c = i('a')
let d = i('b')

// Testing with string literals in objects
type ObjA = { type: 'a' }
type ObjB = { type: 'b' }
type ObjAorB = ObjA | ObjB

function j(x: ObjA): { env: string };
function j(x: ObjB): { data: any[] };
function j(x: ObjAorB) {
  if (x.type === 'a') {
    return { env: 'ObjA' }
  }
  return { data: [] }
}

let e = j({ type: 'a' })
let ff = j({ type: 'b' })

// Testing with more complex objects
interface MyObjA { type: null }
interface MyObjB { type: 'b', data: string }

function fn(x: MyObjA | MyObjB) {
  if (x.type === 'b') {
    console.log(x.data);
  }
  console.log('no data')
}

type StateA = {
  type: undefined;
  currentPage: string;
  pages: any[];
}
type StateB = {
  type: 'batch',
  currentPage: string;
  pages: any[];
  env: null | 'sand' | 'prod';
}
type StateAorB = StateA | StateB

function k(s: StateA): StateA
function k(s: StateB): StateB
function k(s: StateAorB) {
  if (s.type === 'batch') {
    s.
  }
}
```