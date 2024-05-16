TypeError: \"x\" has no properties
==================================

 
The JavaScript exception \"null (or undefined) has no properties\"
occurs when you attempt to access properties of
[`null`](../operators/null) and
[`undefined`](../global_objects/undefined). They don\'t have any.


 
Message
-------

 
```text
TypeError: Cannot read properties of undefined (reading 'x') (V8-based)
TypeError: null has no properties (Firefox)
TypeError: undefined has no properties (Firefox)
TypeError: undefined is not an object (evaluating 'undefined.x') (Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror).



 
What went wrong? 
----------------

 
Both [`null`](../operators/null) and
[`undefined`](../global_objects/undefined), have no properties you could
access.



 
Examples
--------


 
### null and undefined have no properties 

 
 
 
[js]


```js
null.foo;
// TypeError: null has no properties

undefined.bar;
// TypeError: undefined has no properties
```




 
See also 
--------

 
-   [`null`](../operators/null)
-   [`undefined`](../global_objects/undefined)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_properties>

