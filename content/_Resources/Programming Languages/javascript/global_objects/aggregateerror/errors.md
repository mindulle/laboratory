AggregateError: errors
======================


The `errors` data property of an [`AggregateError`](../aggregateerror)
instance contains an array representing the errors that were aggregated.



Value
-----


An [`Array`](../array) containing values in the same order as the
iterable passed as the first argument of the
[`AggregateError()`](aggregateerror) constructor.


Property attributes of `AggregateError: errors`




Writable

yes

Enumerable

no

Configurable

yes


Examples
--------



### Using errors 




[js]


```js
try {
  throw new AggregateError(
    // An iterable of errors
    new Set([new Error("some error"), new Error("another error")]),
    "Multiple errors thrown",
  );
} catch (err) {
  console.log(err.errors);
  // [
  //   Error: some error,
  //   Error: another error
  // ]
}
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-aggregate-error]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-aggregate-error)

  ---------------------------------------------------------------------------------------------------------------


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

`errors`

85

85

79

71

14

85

79

60

14

14.0

85

1.2

15.0.0


See also 
--------


-   [Control flow and error
    handling](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
    guide
-   [`AggregateError`](../aggregateerror)
-   [`Error`: `cause`](../error/cause)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError/errors>

