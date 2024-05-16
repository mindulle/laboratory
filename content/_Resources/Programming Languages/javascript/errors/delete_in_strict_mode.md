SyntaxError: applying the \'delete\' operator to an unqualified name is deprecated
==================================================================================


The JavaScript [strict mode](../strict_mode)-only exception \"applying
the \'delete\' operator to an unqualified name is deprecated\" occurs
when variables are attempted to be deleted using the
[`delete`](../operators/delete) operator.



Message
-------


```text
SyntaxError: Delete of an unqualified identifier in strict mode. (V8-based)
SyntaxError: applying the 'delete' operator to an unqualified name is deprecated (Firefox)
SyntaxError: Cannot delete unqualified property 'a' in strict mode. (Safari)
```




Error type 
----------


[`SyntaxError`](../global_objects/syntaxerror) in [strict
mode](../strict_mode) only.




What went wrong? 
----------------


Normal variables in JavaScript can\'t be deleted using the
[`delete`](../operators/delete) operator. In strict mode, an attempt to
delete a variable will throw an error and is not allowed.

The `delete` operator can only delete properties on an object. Object
properties are \"qualified\" if they are configurable.

Unlike what common belief suggests, the `delete` operator has
**nothing** to do with directly freeing memory. Memory management is
done indirectly via breaking references, see the [memory
management](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_management)
page and the [`delete`](../operators/delete) operator page for more
details.

This error only happens in [strict mode code](../strict_mode). In
non-strict code, the operation just returns `false`.




Examples
--------



### Freeing the contents of a variable 


Attempting to delete a plain variable throws an error in strict mode:



[js]


```js
"use strict";

var x;

// …

delete x;

// SyntaxError: applying the 'delete' operator to an unqualified name
// is deprecated
```


To free the contents of a variable, you can set it to
[`null`](../operators/null):



[js]


```js
"use strict";

var x;

// …

x = null;

// x can be garbage collected
```





See also 
--------


-   [`delete`](../operators/delete)
-   [Memory
    management](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_management)
-   [TypeError: property \"x\" is non-configurable and can\'t be
    deleted](cant_delete)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Delete_in_strict_mode>

