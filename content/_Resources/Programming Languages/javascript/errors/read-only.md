TypeError: \"x\" is read-only
=============================

 
The JavaScript [strict mode](../strict_mode)-only exception \"is
read-only\" occurs when a global variable or object property that was
assigned to is a read-only property.


 
Message
-------

 
```text
TypeError: Cannot assign to read only property 'x' of #<Object> (V8-based)
TypeError: "x" is read-only (Firefox)
TypeError: Attempted to assign to readonly property. (Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror) in [strict
mode](../strict_mode) only.



 
What went wrong? 
----------------

 
The global variable or object property that was assigned to is a
read-only property. (Technically, it is a [non-writable data
property](../global_objects/object/defineproperty#writable_attribute).)

This error happens only in [strict mode code](../strict_mode). In
non-strict code, the assignment is silently ignored.



 
Examples
--------


 
### Invalid cases 

 
Read-only properties are not super common, but they can be created using
[`Object.defineProperty()`](../global_objects/object/defineproperty) or
[`Object.freeze()`](../global_objects/object/freeze).

 
 
[js]


```js
"use strict";
const obj = Object.freeze({ name: "Elsa", score: 157 });
obj.score = 0; // TypeError

("use strict");
Object.defineProperty(this, "LUNG_COUNT", { value: 2, writable: false });
LUNG_COUNT = 3; // TypeError

("use strict");
const frozenArray = Object.freeze([0, 1, 2]);
frozenArray[0]++; // TypeError
```


There are also a few read-only properties built into JavaScript. Maybe
you tried to redefine a mathematical constant.

 
 
[js]


```js
"use strict";
Math.PI = 4; // TypeError
```


Sorry, you can\'t do that.

The global variable `undefined` is also read-only, so you can\'t silence
the infamous \"undefined is not a function\" error by doing this:

 
 
[js]


```js
"use strict";
undefined = function () {}; // TypeError: "undefined" is read-only
```




 
### Valid cases 

 
 
 
[js]


```js
"use strict";
let obj = Object.freeze({ name: "Score", points: 157 });
obj = { name: obj.name, points: 0 }; // replacing it with a new object works
```




 
See also 
--------

 
-   [`Object.defineProperty()`](../global_objects/object/defineproperty)
-   [`Object.freeze()`](../global_objects/object/freeze)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Read-only>

