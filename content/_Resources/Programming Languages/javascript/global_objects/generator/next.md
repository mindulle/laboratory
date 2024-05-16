Generator.prototype.next()
==========================

 
The `next()` method of [`Generator`](../generator) instances returns an
object with two properties `done` and `value`. You can also provide a
parameter to the `next` method to send a value to the generator.


 
Syntax
------

 
 
 
[js]


```js
next()
next(value)
```




 
### Parameters

 

[`value`](#value) [Optional]

:   The value to send to the generator.

    The value will be assigned as a result of a `yield` expression. For
    example, in `variable = yield expression`, the value passed to the
    `.next()` function will be assigned to `variable`.



 
### Return value 

 
An [`Object`](../object) with two properties:

[`done`](#done)

:   A boolean value:

    -   `true` if the generator is past the end of its control flow. In
        this case `value` specifies the *return value* of the generator
        (which may be undefined).
    -   `false` if the generator is able to produce more values.

[`value`](#value_2)

:   Any JavaScript value yielded or returned by the generator.



 
Examples
--------


 
### Using next() 

 
The following example shows a simple generator and the object that the
`next` method returns:

 
 
[js]


```js
function* gen() {
  yield 1;
  yield 2;
  yield 3;
}

const g = gen(); // Generator { }
g.next(); // { value: 1, done: false }
g.next(); // { value: 2, done: false }
g.next(); // { value: 3, done: false }
g.next(); // { value: undefined, done: true }
```




 
### Using next() with a list 

 
In this example, `getPage` takes a list and \"paginates\" it into chunks
of size `pageSize`. Each call to `next` will yield one such chunk.

 
 
[js]


```js
function* getPage(list, pageSize = 1) {
  for (let index = 0; index < list.length; index += pageSize) {
    yield list.slice(index, index + pageSize);
  }
}

const list = [1, 2, 3, 4, 5, 6, 7, 8];
const page = getPage(list, 3); // Generator { }

page.next(); // { value: [1, 2, 3], done: false }
page.next(); // { value: [4, 5, 6], done: false }
page.next(); // { value: [7, 8], done: false }
page.next(); // { value: undefined, done: true }
```




 
### Sending values to the generator 

 
In this example, `next` is called with a value.

 
**Note:** The first call does not log anything, because the generator
was not yielding anything initially.


 
 
[js]


```js
function* gen() {
  while (true) {
    const value = yield;
    console.log(value);
  }
}

const g = gen();
g.next(1); // Returns { value: undefined, done: false }
// No log at this step: the first value sent through `next` is lost
g.next(2); // Returns { value: undefined, done: false }
// Logs 2
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-generator.prototype.next]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-generator.prototype.next)

  -----------------------------------------------------------------------------------------------------------------------------------------


Browser compatibility 
---------------------

 


Desktop

Mobile

Server

Chrome

Edge

Firefox

Opera

Safari

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

WebView Android

Deno

Node.js

`next`

39

13

26

26

10

39

26

26

10

4.0

39

1.0

4.0.0

 
See also 
--------

 
-   [`function*`](../../statements/function*)
-   [Iterators and
    generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    guide



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/next>

