SyntaxError: missing : after property id
========================================

 
The JavaScript exception \"missing : after property id\" occurs when
objects are created using the [object
initializer](../operators/object_initializer) syntax. A colon (`:`)
separates keys and values for the object\'s properties. Somehow, this
colon is missing or misplaced.


 
Message
-------

 
```text
SyntaxError: Invalid shorthand property initializer (V8-based)
SyntaxError: missing : after property id (Firefox)
SyntaxError: Unexpected token '='. Expected a ':' following the property name 'x'. (Safari)
SyntaxError: Unexpected token '+'. Expected an identifier as property name. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
When creating objects with the [object
initializer](../operators/object_initializer) syntax, a colon (`:`)
separates keys and values for the object\'s properties.

 
 
[js]


```js
const obj = { propertyKey: "value" };
```




 
Examples
--------


 
### Colons vs. equal signs 

 
This code fails, as the equal sign can\'t be used this way in this
object initializer syntax.

 
 
[js]


```js
const obj = { propertyKey = "value" };
// SyntaxError: missing : after property id
```


Correct would be to use a colon, or to use square brackets to assign a
new property after the object has been created already.

 
 
[js]


```js
const obj = { propertyKey: "value" };
```


Or alternatively:

 
 
[js]


```js
const obj = {};
obj.propertyKey = "value";
```




 
### Computed properties 

 
If you create a property key from an expression, you need to use square
brackets. Otherwise the property name can\'t be computed:

 
 
[js]


```js
const obj = { "b"+"ar": "foo" };
// SyntaxError: missing : after property id
```


Put the expression in square brackets `[]`:

 
 
[js]


```js
const obj = { ["b" + "ar"]: "foo" };
```




 
See also 
--------

 
-   [Object initializer](../operators/object_initializer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_colon_after_property_id>

