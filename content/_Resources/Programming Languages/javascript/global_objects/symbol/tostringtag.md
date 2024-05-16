Symbol.toStringTag
==================

 
The `Symbol.toStringTag` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@toStringTag`.
[`Object.prototype.toString()`](../object/tostring) looks up this symbol
on the `this` value for the property containing a string that represents
the type of the object.


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@toStringTag`.

 
Property attributes of `Symbol.toStringTag`




Writable

no

Enumerable

no

Configurable

no

 
Examples
--------


 
### Default tags 

 
Some values do not have `Symbol.toStringTag`, but have special
`toString()` representations. For a complete list, see
[`Object.prototype.toString()`](../object/tostring).

 
 
[js]


```js
Object.prototype.toString.call("foo"); // "[object String]"
Object.prototype.toString.call([1, 2]); // "[object Array]"
Object.prototype.toString.call(3); // "[object Number]"
Object.prototype.toString.call(true); // "[object Boolean]"
Object.prototype.toString.call(undefined); // "[object Undefined]"
Object.prototype.toString.call(null); // "[object Null]"
// ... and more
```




 
### Built-in toStringTag symbols 

 
Most built-in objects provide their own `@@toStringTag` property. Almost
all built-in objects\' `@@toStringTag` property is not writable, not
enumerable, and configurable; the exception is
[`Iterator`](../iterator), which is writable for compatibility reasons.

For constructor objects like [`Promise`](../promise), the property is
installed on `Constructor.prototype`, so that all instances of the
constructor inherit `@@toStringTag` and can be stringified. For
non-constructor objects like [`Math`](../math) and [`JSON`](../json),
the property is installed as a static property, so that the namespace
object itself can be stringified. Sometimes, the constructor also
provides its own `toString` method (for example,
[`Intl.Locale`](../intl/locale)), in which case the `@@toStringTag`
property is only used when you explicitly call
`Object.prototype.toString` on it.

 
 
[js]


```js
Object.prototype.toString.call(new Map()); // "[object Map]"
Object.prototype.toString.call(function* () {}); // "[object GeneratorFunction]"
Object.prototype.toString.call(Promise.resolve()); // "[object Promise]"
// ... and more
```




 
### Custom tag with toStringTag 

 
When creating your own class, JavaScript defaults to the \"Object\" tag:

 
 
[js]


```js
class ValidatorClass {}

Object.prototype.toString.call(new ValidatorClass()); // "[object Object]"
```


Now, with the help of `toStringTag`, you are able to set your own custom
tag:

 
 
[js]


```js
class ValidatorClass {
  get [Symbol.toStringTag]() {
    return "Validator";
  }
}

Object.prototype.toString.call(new ValidatorClass()); // "[object Validator]"
```




 
### toStringTag available on all DOM prototype objects 

 
Due to a [WebIDL spec change](https://github.com/whatwg/webidl/pull/357)
in mid-2020, browsers are adding a `Symbol.toStringTag` property to all
DOM prototype objects. For example, to access the `Symbol.toStringTag`
property on
[`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement):

 
 
[js]


```js
const test = document.createElement("button");
test.toString(); // "[object HTMLButtonElement]"
test[Symbol.toStringTag]; // "HTMLButtonElement"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.tostringtag]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.tostringtag)

  ---------------------------------------------------------------------------------------------------------------------


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

`toStringTag`

49

15

51

36

10

49

51

36

10

5.0

49

1.0

6.0.0

`dom_objects`

50

79

78

37

14

50

79

37

14

5.0

50

1.0

No

 
See also 
--------

 
-   [Polyfill of `Symbol.toStringTag` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Object.prototype.toString()`](../object/tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toStringTag>

