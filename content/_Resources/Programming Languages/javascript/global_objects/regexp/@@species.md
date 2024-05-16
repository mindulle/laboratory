RegExp\[@\@species\]
====================

 
The `RegExp[@@species]` static accessor property returns the constructor
used to construct copied regular expressions in certain `RegExp`
methods.

 
**Warning:** The existence of `@@species` allows execution of arbitrary
code and may create security vulnerabilities. It also makes certain
optimizations much harder. Engine implementers are [investigating
whether to remove this
feature](https://github.com/tc39/proposal-rm-builtin-subclassing). Avoid
relying on it if possible.



 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
RegExp[Symbol.species]
```




 
### Return value 

 
The value of the constructor (`this`) on which `get @@species` was
called. The return value is used to construct copied `RegExp` instances.



 
Description
-----------

 
The `@@species` accessor property returns the default constructor for
`RegExp` objects. Subclass constructors may override it to change the
constructor assignment. The default implementation is basically:

 
 
[js]


```js
// Hypothetical underlying implementation for illustration
class RegExp {
  static get [Symbol.species]() {
    return this;
  }
}
```


Because of this polymorphic implementation, `@@species` of derived
subclasses would also return the constructor itself by default.

 
 
[js]


```js
class SubRegExp extends SubRegExp {}
SubRegExp[Symbol.species] === SubRegExp; // true
```


Some `RegExp` methods create a copy of the current regex instance before
running [`exec()`](exec), so that side effects such as changes to
[`lastIndex`](lastindex) are not retained. The `@@species` property is
used to determine the constructor of the new instance. The methods that
copy the current regex instance are:

-   [`[@@matchAll]()`](@@matchall)
-   [`[@@split]()`](@@split)



 
Examples
--------


 
### Species in ordinary objects 

 
The `@@species` property returns the default constructor function, which
is the `RegExp` constructor for `RegExp` objects:

 
 
[js]


```js
RegExp[Symbol.species]; // function RegExp()
```




 
### Species in derived objects 

 
In an instance of a custom `RegExp` subclass, such as `MyRegExp`, the
`MyRegExp` species is the `MyRegExp` constructor. However, you might
want to overwrite this, in order to return parent `RegExp` objects in
your derived class methods:

 
 
[js]


```js
class MyRegExp extends RegExp {
  // Overwrite MyRegExp species to the parent RegExp constructor
  static get [Symbol.species]() {
    return RegExp;
  }
}
```


Or you can use this to observe the copying process:

 
 
[js]


```js
class MyRegExp extends RegExp {
  constructor(...args) {
    console.log("Creating a new MyRegExp instance with args:", args);
    super(...args);
  }
  static get [Symbol.species]() {
    console.log("Copying MyRegExp");
    return this;
  }
  exec(value) {
    console.log("Executing with lastIndex:", this.lastIndex);
    return super.exec(value);
  }
}

Array.from("aabbccdd".matchAll(new MyRegExp("[ac]", "g")));
// Creating a new MyRegExp instance with args: [ '[ac]', 'g' ]
// Copying MyRegExp
// Creating a new MyRegExp instance with args: [ MyRegExp /[ac]/g, 'g' ]
// Executing with lastIndex: 0
// Executing with lastIndex: 1
// Executing with lastIndex: 2
// Executing with lastIndex: 5
// Executing with lastIndex: 6
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp-@\@species]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp-@@species)

  ----------------------------------------------------------------------------------------------------------------------


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

`@@species`

50

13

49

37

10

50

49

37

10

5.0

50

1.0

6.5.0

 
See also 
--------

 
-   [`RegExp`](../regexp)
-   [`Symbol.species`](../symbol/species)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@species>

