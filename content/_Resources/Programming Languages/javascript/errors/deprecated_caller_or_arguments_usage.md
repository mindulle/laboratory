ReferenceError: deprecated caller or arguments usage
====================================================


The JavaScript [strict mode](../strict_mode)-only exception \"deprecated
caller or arguments usage\" occurs when the deprecated
[`Function.prototype.caller`](../global_objects/function/caller) or
[`Function.prototype.arguments`](../global_objects/function/arguments)
properties are used.



Message
-------


```text
TypeError: 'caller', 'callee', and 'arguments' properties may not be accessed on strict mode functions or the arguments objects for calls to them (V8-based & Firefox)
TypeError: 'arguments', 'callee', and 'caller' cannot be accessed in this context. (Safari)
```




Error type 
----------


[`TypeError`](../global_objects/typeerror) in [strict
mode](../strict_mode) only.




What went wrong? 
----------------


In [strict mode](../strict_mode), the
[`Function.prototype.caller`](../global_objects/function/caller) or
[`Function.prototype.arguments`](../global_objects/function/arguments)
properties are used and shouldn\'t be. They are deprecated, because they
leak the function caller, are non-standard, hard to optimize and
potentially a performance-harmful feature.




Examples
--------



### Deprecated function.caller or arguments.callee 


[`Function.prototype.caller`](../global_objects/function/caller) and
[`arguments.callee`](../functions/arguments/callee) are deprecated (see
the reference articles for more information).



[js]


```js
"use strict";

function myFunc() {
  if (myFunc.caller === null) {
    return "The function was called from the top!";
  } else {
    return `This function's caller was ${myFunc.caller}`;
  }
}

myFunc();
// TypeError: 'caller', 'callee', and 'arguments' properties may not be accessed on strict mode functions or the arguments objects for calls to them
```





### Function.prototype.arguments


[`Function.prototype.arguments`](../global_objects/function/arguments)
is deprecated (see the reference article for more information).



[js]


```js
"use strict";

function f(n) {
  g(n - 1);
}

function g(n) {
  console.log(`before: ${g.arguments[0]}`);
  if (n > 0) {
    f(n);
  }
  console.log(`after: ${g.arguments[0]}`);
}

f(2);

console.log(`returned: ${g.arguments}`);
// TypeError: 'caller', 'callee', and 'arguments' properties may not be accessed on strict mode functions or the arguments objects for calls to them
```





See also 
--------


-   [Deprecated and obsolete
    features](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features)
-   [Strict mode](../strict_mode)
-   [`Function.prototype.arguments`](../global_objects/function/arguments)
-   [`Function.prototype.caller`](../global_objects/function/caller)
-   [`arguments.callee`](../functions/arguments/callee)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_caller_or_arguments_usage>

