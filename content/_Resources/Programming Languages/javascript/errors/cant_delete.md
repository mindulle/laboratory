TypeError: property \"x\" is non-configurable and can\'t be deleted
===================================================================


The JavaScript exception \"property is non-configurable and can\'t be
deleted\" occurs when it was attempted to delete a property, but that
property is
[non-configurable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#properties).



Message
-------


```text
TypeError: Cannot delete property 'x' of #<Object> (V8-based)
TypeError: property "x" is non-configurable and can't be deleted (Firefox)
TypeError: Unable to delete property. (Safari)
```




Error type 
----------


[`TypeError`](../global_objects/typeerror) in strict mode only.




What went wrong? 
----------------


It was attempted to delete a property, but that property is
[non-configurable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#properties).
The `configurable` attribute controls whether the property can be
deleted from the object and whether its attributes (other than
`writable`) can be changed.

This error happens only in [strict mode code](../strict_mode). In
non-strict code, the operation returns `false`.




Examples
--------



### Attempting to delete non-configurable properties 


Non-configurable properties are not super common, but they can be
created using
[`Object.defineProperty()`](../global_objects/object/defineproperty) or
[`Object.freeze()`](../global_objects/object/freeze).



[js]


```js
"use strict";
const obj = Object.freeze({ name: "Elsa", score: 157 });
delete obj.score; // TypeError
```




[js]


```js
"use strict";
const obj = {};
Object.defineProperty(obj, "foo", { value: 2, configurable: false });
delete obj.foo; // TypeError
```




[js]


```js
"use strict";
const frozenArray = Object.freeze([0, 1, 2]);
frozenArray.pop(); // TypeError
```


There are also a few non-configurable properties built into JavaScript.
Maybe you tried to delete a mathematical constant.



[js]


```js
"use strict";
delete Math.PI; // TypeError
```





See also 
--------


-   [`delete`](../operators/delete)
-   [`Object.defineProperty()`](../global_objects/object/defineproperty)
-   [`Object.freeze()`](../global_objects/object/freeze)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_delete>

