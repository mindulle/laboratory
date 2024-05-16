Intl.Collator.prototype.resolvedOptions()
=========================================

 
The `resolvedOptions()` method of [`Intl.Collator`](../collator)
instances returns a new object with properties reflecting the locale and
collation options computed during initialization of this collator
object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
resolvedOptions()
```




 
### Parameters

 
None.



 
### Return value 

 
A new object with properties reflecting the locale and collation options
computed during the initialization of the given
[`Intl.Collator`](../collator) object.



 
Description
-----------

 
The resulting object has the following properties:

[`locale`](#locale)

:   The BCP 47 language tag for the locale actually used. If any Unicode
    extension values were requested in the input BCP 47 language tag
    that led to this locale, the key-value pairs that were requested and
    are supported for this locale are included in `locale`.

[`usage`](#usage), `sensitivity`, `ignorePunctuation`

:   The values provided for these properties in the `options` argument
    or filled in as defaults.

[`collation`](#collation)

:   The value requested using the Unicode extension key `"co"`, if it is
    supported for `locale`, or `"default"`.

[`numeric`](#numeric), `caseFirst`

:   The values requested for these properties in the `options` argument
    or using the Unicode extension keys `"kn"` and `"kf"` or filled in
    as defaults. If the implementation does not support these
    properties, they are omitted.



 
Examples
--------


 
### Using the resolvedOptions method 

 
 
 
[js]


```js
const de = new Intl.Collator("de", { sensitivity: "base" });
const usedOptions = de.resolvedOptions();

usedOptions.locale; // "de"
usedOptions.usage; // "sort"
usedOptions.sensitivity; // "base"
usedOptions.ignorePunctuation; // false
usedOptions.collation; // "default"
usedOptions.numeric; // false
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.collator.prototype.resolvedoptions]](https://tc39.es/ecma402/#sec-intl.collator.prototype.resolvedoptions)

  -----------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Intl.Collator`](../collator)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/resolvedOptions>

