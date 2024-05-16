String.prototype.toLocaleUpperCase()
====================================

 
The `toLocaleUpperCase()` method of [`String`](../string) values returns
this string converted to upper case, according to any locale-specific
case mappings.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toLocaleUpperCase()
toLocaleUpperCase(locales)
```




 
### Parameters

 

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag, or an array of such strings.
    Indicates the locale to be used to convert to upper case according
    to any locale-specific case mappings. For the general form and
    interpretation of the `locales` argument, see [the parameter
    description on the `Intl` main page](../intl#locales_argument).

    Unlike other methods that use the `locales` argument,
    `toLocaleUpperCase()` does not allow locale matching. Therefore,
    after checking the validity of the `locales` argument,
    `toLocaleUpperCase()` always uses the first locale in the list (or
    the default locale if the list is empty), even if this locale is not
    supported by the implementation.



 
### Return value 

 
A new string representing the calling string converted to upper case,
according to any locale-specific case mappings.



 
Description
-----------

 
The `toLocaleUpperCase()` method returns the value of the string
converted to upper case according to any locale-specific case mappings.
`toLocaleUpperCase()` does not affect the value of the string itself. In
most cases, this will produce the same result as
[`toUpperCase()`](touppercase), but for some locales, such as Turkish,
whose case mappings do not follow the default case mappings in Unicode,
there may be a different result.

Also notice that conversion is not necessarily a 1:1 character mapping,
as some characters might result in two (or even more) characters when
transformed to upper-case. Therefore the length of the result string can
differ from the input length. This also implies that the conversion is
not stable, so i.E. the following can return `false`:
`x.toLocaleLowerCase() === x.toLocaleUpperCase().toLocaleLowerCase()`



 
Examples
--------


 
### Using toLocaleUpperCase() 

 
 
 
[js]


```js
"alphabet".toLocaleUpperCase(); // 'ALPHABET'

"Gesäß".toLocaleUpperCase(); // 'GESÄSS'

"i\u0307".toLocaleUpperCase("lt-LT"); // 'I'

const locales = ["lt", "LT", "lt-LT", "lt-u-co-phonebk", "lt-x-lietuva"];
"i\u0307".toLocaleUpperCase(locales); // 'I'
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.tolocaleuppercase]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.tolocaleuppercase)

  [ECMAScript Internationalization API Specification\
  [\# sup-string.prototype.tolocaleuppercase]](https://tc39.es/ecma402/#sup-string.prototype.tolocaleuppercase)
  -------------------------------------------------------------------------------------------------------------------------------------------------


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

`toLocaleUpperCase`

1

12

1

4

1.3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`locale`

58

12

55

45

10

58

55

42

10

7.0

58

1.8

1.0--1.8Only the locale data for `en-US` is available.

13.0.0

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the function
silently falls back to `en-US`. To make full ICU (locale) data available
before version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

 
See also 
--------

 
-   [`String.prototype.toLocaleLowerCase()`](tolocalelowercase)
-   [`String.prototype.toLowerCase()`](tolowercase)
-   [`String.prototype.toUpperCase()`](touppercase)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLocaleUpperCase>

