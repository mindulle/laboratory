TypeError: \'x\' is not iterable
================================

 
The JavaScript exception \"is not iterable\" occurs when the value which
is given as the right-hand side of
[`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...of_statement),
as argument of a function such as
[`Promise.all`](../global_objects/promise/all) or
[`TypedArray.from`](../global_objects/typedarray/from), or as the
right-hand side of an array [destructuring
assignment](../operators/destructuring_assignment), is not an [iterable
object](../iteration_protocols).


 
Message
-------

 
```text
TypeError: object is not iterable (cannot read property Symbol(Symbol.iterator)) (V8-based)
TypeError: x is not iterable (Firefox)
TypeError: undefined is not a function (near '...[x]...') (Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror)



 
What went wrong? 
----------------

 
The value which is given as the right-hand side of
[`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...of_statement),
or as argument of a function such as
[`Promise.all`](../global_objects/promise/all) or
[`TypedArray.from`](../global_objects/typedarray/from), or as the
right-hand side of an array [destructuring
assignment](../operators/destructuring_assignment), is not an [iterable
object](../iteration_protocols). An iterable can be a built-in iterable
type such as [`Array`](../global_objects/array),
[`String`](../global_objects/string) or [`Map`](../global_objects/map),
a generator result, or an object implementing the [iterable
protocol](../iteration_protocols#the_iterable_protocol).



 
Examples
--------


 
### Array destructuring a non-iterable 

 
 
 
[js]


```js
const myobj = { arrayOrObjProp1: {}, arrayOrObjProp2: [42] };

const {
  arrayOrObjProp1: [value1],
  arrayOrObjProp2: [value2],
} = myobj; // TypeError: object is not iterable

console.log(value1, value2);
```


The non-iterable might turn to be `undefined` in some runtime
environments.



 
### Iterating over Object properties 

 
In JavaScript, [`Object`](../global_objects/object)s are not iterable
unless they implement the [iterable
protocol](../iteration_protocols#the_iterable_protocol). Therefore, you
cannot use
[`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...of_statement)
to iterate over the properties of an object.

 
 
[js]


```js
const obj = { France: "Paris", England: "London" };
for (const p of obj) {
  // …
} // TypeError: obj is not iterable
```


Instead you have to use [`Object.keys`](../global_objects/object/keys)
or [`Object.entries`](../global_objects/object/entries), to iterate over
the properties or entries of an object.

 
 
[js]


```js
const obj = { France: "Paris", England: "London" };
// Iterate over the property names:
for (const country of Object.keys(obj)) {
  const capital = obj[country];
  console.log(country, capital);
}

for (const [country, capital] of Object.entries(obj)) {
  console.log(country, capital);
}
```


Another option for this use case might be to use a
[`Map`](../global_objects/map):

 
 
[js]


```js
const map = new Map();
map.set("France", "Paris");
map.set("England", "London");
// Iterate over the property names:
for (const country of map.keys()) {
  const capital = map.get(country);
  console.log(country, capital);
}

for (const capital of map.values()) {
  console.log(capital);
}

for (const [country, capital] of map.entries()) {
  console.log(country, capital);
}
```




 
### Iterating over a generator 

 
[Generator
functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators#generator_functions)
are functions you call to produce an iterable object.

 
 
[js]


```js
function* generate(a, b) {
  yield a;
  yield b;
}

for (const x of generate) {
  console.log(x);
} // TypeError: generate is not iterable
```


When they are not called, the [`Function`](../global_objects/function)
object corresponding to the generator is callable, but not iterable.
Calling a generator produces an iterable object which will iterate over
the values yielded during the execution of the generator.

 
 
[js]


```js
function* generate(a, b) {
  yield a;
  yield b;
}

for (const x of generate(1, 2)) {
  console.log(x);
}
```




 
### Iterating over a custom iterable 

 
Custom iterables can be created by implementing the
[`Symbol.iterator`](../global_objects/symbol/iterator) method. You must
be certain that your iterator method returns an object which is an
iterator, which is to say it must have a next method.

 
 
[js]


```js
const myEmptyIterable = {
  [Symbol.iterator]() {
    return []; // [] is iterable, but it is not an iterator — it has no next method.
  },
};

Array.from(myEmptyIterable); // TypeError: myEmptyIterable is not iterable
```


Here is a correct implementation:

 
 
[js]


```js
const myEmptyIterable = {
  [Symbol.iterator]() {
    return [][Symbol.iterator]();
  },
};

Array.from(myEmptyIterable); // []
```




 
See also 
--------

 
-   [Iterable protocol](../iteration_protocols#the_iterable_protocol)
-   [`Object.keys`](../global_objects/object/keys)
-   [`Object.entries`](../global_objects/object/entries)
-   [`Map`](../global_objects/map)
-   [Generator
    functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators#generator_functions)
-   [for\...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...of_statement)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/is_not_iterable>

