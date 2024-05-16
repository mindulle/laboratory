Array.prototype.toLocaleString()
================================


The `toLocaleString()` method of [`Array`](../array) instances returns a
string representing the elements of the array. The elements are
converted to strings using their `toLocaleString` methods and these
strings are separated by a locale-specific string (such as a comma
\",\").



Try it 
------






Syntax
------




[js]


```js
toLocaleString()
toLocaleString(locales)
toLocaleString(locales, options)
```





### Parameters



[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag, or an array of such strings.
    For the general form and interpretation of the `locales` argument,
    see [the parameter description on the `Intl` main
    page](../intl#locales_argument).

[`options`](#options) [Optional]

:   An object with configuration properties. For numbers, see
    [`Number.prototype.toLocaleString()`](../number/tolocalestring); for
    dates, see
    [`Date.prototype.toLocaleString()`](../date/tolocalestring).




### Return value 


A string representing the elements of the array.




Description
-----------


The `Array.prototype.toLocaleString` method traverses its content,
calling the `toLocaleString` method of every element with the `locales`
and `options` parameters provided, and concatenates them with an
implementation-defined separator (such as a comma \",\"). Note that the
method itself does not consume the two parameters --- it only passes
them to the `toLocaleString()` of each element. The choice of the
separator string depends on the host\'s current locale, not the
`locales` parameter.

If an element is `undefined`, `null`, it is converted to an empty string
instead of the string `"null"` or `"undefined"`.

When used on [sparse
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the `toLocaleString()` method iterates empty slots as if they have the
value `undefined`.

The `toLocaleString()` method is
[generic](../array#generic_array_methods). It only expects the `this`
value to have a `length` property and integer-keyed properties.




Examples
--------



### Using locales and options 


The elements of the array are converted to strings using their
`toLocaleString` methods.

-   `Object`:
    [`Object.prototype.toLocaleString()`](../object/tolocalestring)
-   `Number`:
    [`Number.prototype.toLocaleString()`](../number/tolocalestring)
-   `Date`: [`Date.prototype.toLocaleString()`](../date/tolocalestring)

Always display the currency for the strings and numbers in the `prices`
array:



[js]


```js
const prices = ["￥7", 500, 8123, 12];
prices.toLocaleString("ja-JP", { style: "currency", currency: "JPY" });

// "￥7,￥500,￥8,123,￥12"
```


For more examples, see also the
[`Intl.NumberFormat`](../intl/numberformat) and
[`Intl.DateTimeFormat`](../intl/datetimeformat) pages.




### Using toLocaleString() on sparse arrays 


`toLocaleString()` treats empty slots the same as `undefined` and
produces an extra separator:



[js]


```js
console.log([1, , 3].toLocaleString()); // '1,,3'
```





### Calling toLocaleString() on non-array objects 


The `toLocaleString()` method reads the `length` property of `this` and
then accesses each property whose key is a nonnegative integer less than
`length`.



[js]


```js
const arrayLike = {
  length: 3,
  0: 1,
  1: 2,
  2: 3,
  3: 4, // ignored by toLocaleString() since length is 3
};
console.log(Array.prototype.toLocaleString.call(arrayLike));
// 1,2,3
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.tolocalestring]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.tolocalestring)

  [ECMAScript Internationalization API Specification\
  [\# sup-array.prototype.tolocalestring]](https://tc39.es/ecma402/#sup-array.prototype.tolocalestring)
  ---------------------------------------------------------------------------------------------------------------------------------------------


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

`toLocaleString`

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

≤37

1.0

0.10.0

`locales_parameter`

24

79

52

15

7

25

56

14

7

2.0

4.4

1.8

1.0--1.8Only the locale data for `en-US` is available.

13.0.0

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the function
silently falls back to `en-US`. To make full ICU (locale) data available
before version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`options_parameter`

24

79

52

15

7

25

56

14

7

2.0

4.4

1.0

0.12.0


See also 
--------


-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.toString()`](tostring)
-   [`TypedArray.prototype.toLocaleString()`](../typedarray/tolocalestring)
-   [`Intl`](../intl)
-   [`Intl.ListFormat`](../intl/listformat)
-   [`Object.prototype.toLocaleString()`](../object/tolocalestring)
-   [`Number.prototype.toLocaleString()`](../number/tolocalestring)
-   [`Date.prototype.toLocaleString()`](../date/tolocalestring)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toLocaleString>

