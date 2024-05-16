SyntaxError: getter and setter for private name \#x should either be both static or non-static
==============================================================================================


The JavaScript exception \"mismatched placement\" occurs when a private
[getter](../functions/get) and [setter](../functions/set) are mismatched
in whether or not they are [`static`](../classes/static).



Message
-------


```text
SyntaxError: Identifier '#x' has already been declared (V8-based)
SyntaxError: getter and setter for private name #x should either be both static or non-static (Firefox)
SyntaxError: Cannot declare a private non-static getter if there is a static private setter with used name. (Safari)
```




Error type 
----------


[`SyntaxError`](../global_objects/syntaxerror)




What went wrong? 
----------------


Private [getters](../functions/get) and [setters](../functions/set) for
the same name must either be both [`static`](../classes/static), or both
non-static. This limitation does not exist for public methods.




Examples
--------



### Mismatched placement 




[js]


```js
class Test {
  static set #foo(_) {}
  get #foo() {}
}

// SyntaxError: getter and setter for private name #foo should either be both static or non-static
```


Since `foo` is [private](privateProperties.md), the methods
must be either both [`static`](../classes/static):



[js]


```js
class Test {
  static set #foo(_) {}
  static get #foo() {}
}
```


or non-static:



[js]


```js
class Test {
  set #foo(_) {}
  get #foo() {}
}
```





See also 
--------


-   [`get`](../functions/get)
-   [`set`](../functions/set)
-   [`static`](../classes/static)
-   [Private properties](privateProperties.md)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Either_be_both_static_or_non-static>

