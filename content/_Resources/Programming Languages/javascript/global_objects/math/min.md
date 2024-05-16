Math.min()
==========

 
The `Math.min()` static method returns the smallest of the numbers given
as input parameters, or [`Infinity`](../infinity) if there are no
parameters.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.min()
Math.min(value1)
Math.min(value1, value2)
Math.min(value1, value2, /* …, */ valueN)
```




 
### Parameters

 

[`value1`](#value1), ..., `valueN`

:   Zero or more numbers among which the lowest value will be selected
    and returned.



 
### Return value 

 
The smallest of the given numbers. Returns [`NaN`](../nan) if any of the
parameters is or is converted into `NaN`. Returns
[`Infinity`](../infinity) if no parameters are provided.



 
Description
-----------

 
Because `min()` is a static method of `Math`, you always use it as
`Math.min()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).

[`Math.min.length`](../function/length) is 2, which weakly signals that
it\'s designed to handle at least two parameters.



 
Examples
--------


 
### Using Math.min() 

 
This finds the min of `x` and `y` and assigns it to `z`:

 
 
[js]


```js
const x = 10;
const y = -20;
const z = Math.min(x, y); // -20
```




 
### Clipping a value with Math.min() 

 
`Math.min()` is often used to clip a value so that it is always less
than or equal to a boundary. For instance, this

 
 
[js]


```js
let x = f(foo);

if (x > boundary) {
  x = boundary;
}
```


may be written as this

 
 
[js]


```js
const x = Math.min(f(foo), boundary);
```


[`Math.max()`](max) can be used in a similar way to clip a value at the
other end.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.min]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.min)

  -----------------------------------------------------------------------------------------------


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

`min`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`Math.max()`](max)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min>

