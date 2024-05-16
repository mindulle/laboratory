Intl.Collator
=============

 
The `Intl.Collator` object enables language-sensitive string comparison.


 
Try it 
------

 



 
Constructor
-----------

 

[`Intl.Collator()`](collator/collator)

:   Creates a new `Collator` object.



 
Static methods 
--------------

 

[`Intl.Collator.supportedLocalesOf()`](collator/supportedlocalesof)

:   Returns an array containing those of the provided locales that are
    supported without having to fall back to the runtime\'s default
    locale.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.Collator.prototype` and shared by
all `Intl.Collator` instances.

[`Intl.Collator.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.Collator` instances, the initial value is the
    [`Intl.Collator`](collator/collator) constructor.

[`Intl.Collator.prototype[@@toStringTag]`](#intl.collator.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.Collator"`. This property is used in
    [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.Collator.prototype.compare()`](collator/compare)

:   Getter function that compares two strings according to the sort
    order of this [`Intl.Collator`](collator) object.

[`Intl.Collator.prototype.resolvedOptions()`](collator/resolvedoptions)

:   Returns a new object with properties reflecting the locale and
    collation options computed during initialization of the object.



 
Examples
--------


 
### Using Collator 

 
The following example demonstrates the different potential results for a
string occurring before, after, or at the same level as another:

 
 
[js]


```js
console.log(new Intl.Collator().compare("a", "c")); // -1, or some other negative value
console.log(new Intl.Collator().compare("c", "a")); // 1, or some other positive value
console.log(new Intl.Collator().compare("a", "a")); // 0
```


Note that the results shown in the code above can vary between browsers
and browser versions. This is because the values are
implementation-specific. That is, the specification requires only that
the before and after values are negative and positive.



 
### Using locales 

 
The results provided by
[`Intl.Collator.prototype.compare()`](collator/compare) vary between
languages. In order to get the sort order of the language used in the
user interface of your application, make sure to specify that language
(and possibly some fallback languages) using the `locales` argument:

 
 
[js]


```js
// in German, ä sorts with a
console.log(new Intl.Collator("de").compare("ä", "z"));
// -1, or some other negative value

// in Swedish, ä sorts after z
console.log(new Intl.Collator("sv").compare("ä", "z"));
// 1, or some other positive value
```




 
### Using options 

 
The results provided by
[`Intl.Collator.prototype.compare()`](collator/compare) can be
customized using the `options` argument:

 
 
[js]


```js
// in German, ä has a as the base letter
console.log(new Intl.Collator("de", { sensitivity: "base" }).compare("ä", "a"));
// 0

// in Swedish, ä and a are separate base letters
console.log(new Intl.Collator("sv", { sensitivity: "base" }).compare("ä", "a"));
// 1, or some other positive value
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  collator-objects]](https://tc39.es/ecma402/#collator-objects)

  -----------------------------------------------------------------------


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

`Collator`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

13.0.0

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the `Collator`
instance silently falls back to `en-US`. To make full ICU (locale) data
available before version 13, see [Node.js documentation on the
`--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`Collator`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `Collator()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/Collator)
for more details.

`compare`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `Collator()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/Collator)
for more details.

`resolvedOptions`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `Collator()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/Collator)
for more details.

`supportedLocalesOf`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

13.0.0

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. To make full ICU (locale) data available before
version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

 
See also 
--------

 
-   [`Intl`](../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator>

