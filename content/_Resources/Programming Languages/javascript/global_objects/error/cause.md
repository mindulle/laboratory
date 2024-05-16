Error: cause
============

 
The `cause` data property of an [`Error`](../error) instance indicates
the specific original cause of the error.

It is used when catching and re-throwing an error with a more-specific
or useful error message in order to still have access to the original
error.


 
Value
-----

 
The value that was passed to the [`Error()`](error) constructor in the
`options.cause` argument. It may not be present.

 
Property attributes of `Error: cause`




Writable

yes

Enumerable

no

Configurable

yes

 
Description
-----------

 
The value of `cause` can be of any type. You should not make assumptions
that the error you caught has an `Error` as its `cause`, in the same way
that you cannot be sure the variable bound in the `catch` statement is
an `Error` either. The \"Providing structured data as the error cause\"
example below shows a case where a non-error is deliberately provided as
the cause.



 
Examples
--------


 
### Rethrowing an error with a cause 

 
It is sometimes useful to catch an error and re-throw it with a new
message. In this case you should pass the original error into the
constructor for the new `Error`, as shown.

 
 
[js]


```js
try {
  connectToDatabase();
} catch (err) {
  throw new Error("Connecting to database failed.", { cause: err });
}
```


For a more detailed example see [Error \> Differentiate between similar
errors](../error#differentiate_between_similar_errors).



 
### Providing structured data as the error cause 

 
Error messages written for human consumption may be inappropriate for
machine parsing --- since they\'re subject to rewording or punctuation
changes that may break any existing parsing written to consume them. So
when throwing an error from a function, as an alternative to a
human-readable error message, you can instead provide the cause as
structured data, for machine parsing.

 
 
[js]


```js
function makeRSA(p, q) {
  if (!Number.isInteger(p) || !Number.isInteger(q)) {
    throw new Error("RSA key generation requires integer inputs.", {
      cause: { code: "NonInteger", values: [p, q] },
    });
  }
  if (!areCoprime(p, q)) {
    throw new Error("RSA key generation requires two co-prime integers.", {
      cause: { code: "NonCoprime", values: [p, q] },
    });
  }
  // rsa algorithm…
}
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-installerrorcause]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-installerrorcause)

  -------------------------------------------------------------------------------------------------------------------


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

`cause`

93

93

91

79

15

93

91

66

15

17.0

93

1.13

16.9.0

`displayed_in_console`

No

No

91

No

No

No

91

No

No

No

No

1.13

16.9.0

 
See also 
--------

 
-   [`Error.prototype.message`](message)
-   [`Error.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/cause>

