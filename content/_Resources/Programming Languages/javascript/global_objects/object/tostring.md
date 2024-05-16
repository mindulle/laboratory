Object.prototype.toString()
===========================

 
The `toString()` method of [`Object`](../object) instances returns a
string representing this object. This method is meant to be overridden
by derived objects for custom [type
coercion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion)
logic.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toString()
```




 
### Parameters

 
By default `toString()` takes no parameters. However, objects that
inherit from `Object` may override it with their own implementations
that do take parameters. For example, the
[`Number.prototype.toString()`](../number/tostring) and
[`BigInt.prototype.toString()`](../bigint/tostring) methods take an
optional `radix` parameter.



 
### Return value 

 
A string representing the object.



 
Description
-----------

 
JavaScript calls the `toString` method to [convert an object to a
primitive
value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion).
You rarely need to invoke the `toString` method yourself; JavaScript
automatically invokes it when encountering an object where a primitive
value is expected.

This method is called in priority by [string
conversion](../string#string_coercion), but [numeric
conversion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and [primitive
conversion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_coercion)
call `valueOf()` in priority. However, because the base
[`valueOf()`](valueof) method returns an object, the `toString()` method
is usually called in the end, unless the object overrides `valueOf()`.
For example, `+[1]` returns `1`, because its
[`toString()`](../array/tostring) method returns `"1"`, which is then
converted to a number.

All objects that inherit from `Object.prototype` (that is, all except
[`null`-prototype objects](../object#null-prototype_objects)) inherit
the `toString()` method. When you create a custom object, you can
override `toString()` to call a custom method, so that your custom
object can be converted to a string value. Alternatively, you can add a
[`@@toPrimitive`](../symbol/toprimitive) method, which allows even more
control over the conversion process, and will always be preferred over
`valueOf` or `toString` for any type conversion.

To use the base `Object.prototype.toString()` with an object that has it
overridden (or to invoke it on `null` or `undefined`), you need to call
[`Function.prototype.call()`](../function/call) or
[`Function.prototype.apply()`](../function/apply) on it, passing the
object you want to inspect as the first parameter (called `thisArg`).

 
 
[js]


```js
const arr = [1, 2, 3];

arr.toString(); // "1,2,3"
Object.prototype.toString.call(arr); // "[object Array]"
```


`Object.prototype.toString()` returns `"[object Type]"`, where `Type` is
the object type. If the object has a
[`Symbol.toStringTag`](../symbol/tostringtag) property whose value is a
string, that value will be used as the `Type`. Many built-in objects,
including [`Map`](../map) and [`Symbol`](../symbol), have a
`Symbol.toStringTag`. Some objects predating ES6 do not have
`Symbol.toStringTag`, but have a special tag nonetheless. They include
(the tag is the same as the type name given below):

-   [`Array`](../array)
-   [`Function`](../../functions) (anything whose
    [`typeof`](../../operators/typeof) returns `"function"`)
-   [`Error`](../error)
-   [`Boolean`](../boolean)
-   [`Number`](../number)
-   [`String`](../string)
-   [`Date`](../date)
-   [`RegExp`](../regexp)

The [`arguments`](../../functions/arguments) object returns
`"[object Arguments]"`. Everything else, including user-defined classes,
unless with a custom `Symbol.toStringTag`, will return
`"[object Object]"`.

`Object.prototype.toString()` invoked on [`null`](../../operators/null)
and [`undefined`](../undefined) returns `[object Null]` and
`[object Undefined]`, respectively.



 
Examples
--------


 
### Overriding toString for custom objects 

 
You can create a function to be called in place of the default
`toString()` method. The `toString()` function you create should return
a string value. If it returns an object and the method is called
implicitly during [type
conversion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion),
then its result is ignored and the value of a related method,
[`valueOf()`](valueof), is used instead, or a `TypeError` is thrown if
none of these methods return a primitive.

The following code defines a `Dog` class.

 
 
[js]


```js
class Dog {
  constructor(name, breed, color, sex) {
    this.name = name;
    this.breed = breed;
    this.color = color;
    this.sex = sex;
  }
}
```


If you call the `toString()` method, either explicitly or implicitly, on
an instance of `Dog`, it returns the default value inherited from
[`Object`](../object):

 
 
[js]


```js
const theDog = new Dog("Gabby", "Lab", "chocolate", "female");

theDog.toString(); // "[object Object]"
`${theDog}`; // "[object Object]"
```


The following code overrides the default `toString()` method. This
method generates a string containing the `name`, `breed`, `color`, and
`sex` of the object.

 
 
[js]


```js
class Dog {
  constructor(name, breed, color, sex) {
    this.name = name;
    this.breed = breed;
    this.color = color;
    this.sex = sex;
  }
  toString() {
    return `Dog ${this.name} is a ${this.sex}${this.color}${this.breed}`;
  }
}
```


With the preceding code in place, any time an instance of `Dog` is used
in a string context, JavaScript automatically calls the `toString()`
method.

 
 
[js]


```js
const theDog = new Dog("Gabby", "Lab", "chocolate", "female");

`${theDog}`; // "Dog Gabby is a female chocolate Lab"
```




 
### Using toString() to detect object class 

 
`toString()` can be used with every object and (by default) allows you
to get its class.

 
 
[js]


```js
const toString = Object.prototype.toString;

toString.call(new Date()); // [object Date]
toString.call(new String()); // [object String]
// Math has its Symbol.toStringTag
toString.call(Math); // [object Math]

toString.call(undefined); // [object Undefined]
toString.call(null); // [object Null]
```


Using `toString()` in this way is unreliable; objects can change the
behavior of `Object.prototype.toString()` by defining a
[`Symbol.toStringTag`](../symbol/tostringtag) property, leading to
unexpected results. For example:

 
 
[js]


```js
const myDate = new Date();
Object.prototype.toString.call(myDate); // [object Date]

myDate[Symbol.toStringTag] = "myDate";
Object.prototype.toString.call(myDate); // [object myDate]

Date.prototype[Symbol.toStringTag] = "prototype polluted";
Object.prototype.toString.call(new Date()); // [object prototype polluted]
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.prototype.tostring]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.prototype.tostring)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`toString`

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

 
-   [Polyfill of `Object.prototype.toString` with `Symbol.toStringTag`
    support in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.prototype.valueOf()`](valueof)
-   [`Number.prototype.toString()`](../number/tostring)
-   [`Symbol.toPrimitive`](../symbol/toprimitive)
-   [`Symbol.toStringTag`](../symbol/tostringtag)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toString>

