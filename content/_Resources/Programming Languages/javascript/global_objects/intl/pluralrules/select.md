Intl.PluralRules.prototype.select()
===================================

 
The `select()` method of [`Intl.PluralRules`](../pluralrules) instances
returns a string indicating which plural rule to use for locale-aware
formatting of a number.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
select(number)
```




 
### Parameters

 

[`number`](#number)

:   The number to get a plural rule for.



 
### Return value 

 
A string representing the pluralization category of the `number`. This
can be one of `zero`, `one`, `two`, `few`, `many`, or `other`.



 
Description
-----------

 
This function selects a pluralization category according to the locale
and formatting options of an [`Intl.PluralRules`](../pluralrules)
object. These options are set in the [`Intl.PluralRules()`](pluralrules)
constructor.



 
Examples
--------


 
### Using select() 

 
First, create an `Intl.PluralRules` object, passing the appropriate
`locales` and `options` parameters. Here we create a plural rules object
for Arabic in the Egyptian dialect. Because the `type` is not specified
the rules object will provide formatting for cardinal numbers (the
default).

 
 
[js]


```js
const pr = new Intl.PluralRules("ar-EG");
```


Then call `select()` on the rules object, specifying the number for
which the plural form is required. Note that Arabic has 5 forms for
cardinal numbers, as shown.

 
 
[js]


```js
pr.select(0); // 'zero'
pr.select(1); // 'one'
pr.select(2); // 'two'
pr.select(6); // 'few'
pr.select(18); // 'many'
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.pluralrules.prototype.select]](https://tc39.es/ecma402/#sec-intl.pluralrules.prototype.select)

  -----------------------------------------------------------------------------------------------------------------


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

`select`

63

18

58

50

13

63

58

46

13

8.0

63

1.8

10.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `PluralRules()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/PluralRules)
for more details.

 
See also 
--------

 
-   [`Intl.PluralRules`](../pluralrules)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/select>

