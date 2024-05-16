TypeError: invalid Array.prototype.sort argument
================================================

 
The JavaScript exception \"invalid Array.prototype.sort argument\"
occurs when the argument of
[`Array.prototype.sort()`](../global_objects/array/sort) isn\'t either
[`undefined`](../global_objects/undefined) or a function which compares
its operands.


 
Message
-------

 
```text
TypeError: The comparison function must be either a function or undefined (V8-based)
TypeError: invalid Array.prototype.sort argument (Firefox)
TypeError: Array.prototype.sort requires the comparator argument to be a function or undefined (Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror)



 
What went wrong? 
----------------

 
The argument of [`Array.prototype.sort()`](../global_objects/array/sort)
is expected to be either [`undefined`](../global_objects/undefined) or a
function which compares its operands.



 
Examples
--------


 
### Invalid cases 

 
 
 
[js]


```js
[1, 3, 2].sort(5); // TypeError
```




 
### Valid cases 

 
 
 
[js]


```js
[1, 3, 2].sort(); // [1, 2, 3]
[1, 3, 2].sort((a, b) => a - b); // [1, 2, 3]
```




 
See also 
--------

 
-   [`Array.prototype.sort()`](../global_objects/array/sort)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Array_sort_argument>

