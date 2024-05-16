Boolean() constructor
=====================


The `Boolean()` constructor creates [`Boolean`](../boolean) objects.
When called as a function, it returns primitive values of type Boolean.



Try it 
------






Syntax
------




[js]


```js
new Boolean(value)
Boolean(value)
```


 
**Note:** `Boolean()` can be called with or without
[`new`](../../operators/new), but with different effects. See [Return
value](#return_value).





### Parameters



[`value`](#value)

:   The initial value of the `Boolean` object.




### Return value 


When `Boolean()` is called as a constructor (with
[`new`](../../operators/new)), it creates a [`Boolean`](../boolean)
object, which is **not** a primitive.

When `Boolean()` is called as a function (without `new`), it coerces the
parameter to a boolean primitive.

 
**Warning:** You should rarely find yourself using `Boolean` as a
constructor.





Description
-----------


The value passed as the first parameter is [converted to a boolean
value](../boolean#boolean_coercion). If the value is omitted or is `0`,
`-0`, `0n`, [`null`](../../operators/null), `false`, [`NaN`](../nan),
[`undefined`](../undefined), or the empty string (`""`), then the object
has an initial value of `false`. All other values, including any object,
an empty array (`[]`), or the string `"false"`, create an object with an
initial value of `true`.

 
**Note:** When the non-standard property
[`document.all`](https://developer.mozilla.org/en-US/docs/Web/API/Document/all)
is used as an argument for this constructor, the result is a `Boolean`
object with the value `false`. This property is legacy and non-standard
and should not be used.





Examples
--------



### Creating Boolean objects with an initial value of false 




[js]


```js
const bZero = new Boolean(0);
const bNull = new Boolean(null);
const bEmptyString = new Boolean("");
const bfalse = new Boolean(false);

typeof bfalse; // "object"
Boolean(bfalse); // true
```


Note how converting a `Boolean` object to a primitive with `Boolean()`
always yields `true`, even if the object holds a value of `false`. You
are therefore always advised to avoid constructing `Boolean` wrapper
objects.

If you need to take the primitive value out from the wrapper object,
instead of using the `Boolean()` function, use the object\'s
[`valueOf()`](valueof) method instead.



[js]


```js
const bfalse = new Boolean(false);

bfalse.valueOf(); // false
```





### Creating `Boolean` objects with an initial value of `true` 




[js]


```js
const btrue = new Boolean(true);
const btrueString = new Boolean("true");
const bfalseString = new Boolean("false");
const bSuLin = new Boolean("Su Lin");
const bArrayProto = new Boolean([]);
const bObjProto = new Boolean({});
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-boolean-constructor]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-boolean-constructor)

  -----------------------------------------------------------------------------------------------------------------------


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

`Boolean`

1

12

1

4

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


-   [Boolean](https://developer.mozilla.org/en-US/docs/Glossary/Boolean)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/Boolean>

