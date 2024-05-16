Error
=====

 
`Error` objects are thrown when runtime errors occur. The `Error` object
can also be used as a base object for user-defined exceptions. See below
for standard built-in error types.


 
Description
-----------

 
Runtime errors result in new `Error` objects being created and thrown.

`Error` is a [serializable
object](https://developer.mozilla.org/en-US/docs/Glossary/Serializable_object),
so it can be cloned with
[`structuredClone()`](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone)
or copied between
[Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) using
[`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage).



 
### Error types 

 
Besides the generic `Error` constructor, there are other core error
constructors in JavaScript. For client-side exceptions, see [Exception
handling
statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling#exception_handling_statements).

[`EvalError`](evalerror)

:   Creates an instance representing an error that occurs regarding the
    global function [`eval()`](eval).

[`RangeError`](rangeerror)

:   Creates an instance representing an error that occurs when a numeric
    variable or parameter is outside its valid range.

[`ReferenceError`](referenceerror)

:   Creates an instance representing an error that occurs when
    de-referencing an invalid reference.

[`SyntaxError`](syntaxerror)

:   Creates an instance representing a syntax error.

[`TypeError`](typeerror)

:   Creates an instance representing an error that occurs when a
    variable or parameter is not of a valid type.

[`URIError`](urierror)

:   Creates an instance representing an error that occurs when
    [`encodeURI()`](encodeuri) or [`decodeURI()`](decodeuri) are passed
    invalid parameters.

[`AggregateError`](aggregateerror)

:   Creates an instance representing several errors wrapped in a single
    error when multiple errors need to be reported by an operation, for
    example by [`Promise.any()`](promise/any).

[`InternalError`](internalerror) [Non-standard]

:   Creates an instance representing an error that occurs when an
    internal error in the JavaScript engine is thrown. E.g. \"too much
    recursion\".



 
Constructor
-----------

 

[`Error()`](error/error)

:   Creates a new `Error` object.



 
Static methods 
--------------

 

[`Error.captureStackTrace()`](#error.capturestacktrace) [Non-standard]

:   A non-standard V8 function that creates the [`stack`](error/stack)
    property on an Error instance.

[`Error.stackTraceLimit`](#error.stacktracelimit) [Non-standard]

:   A non-standard V8 numerical property that limits how many stack
    frames to include in an error stacktrace.

[`Error.prepareStackTrace()`](#error.preparestacktrace) [Non-standard]

:   A non-standard V8 function that, if provided by usercode, is called
    by the V8 JavaScript engine for thrown exceptions, allowing the user
    to provide custom formatting for stacktraces.



 
Instance properties 
-------------------

 
These properties are defined on `Error.prototype` and shared by all
`Error` instances.

[`Error.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Error` instances, the initial value is the [`Error`](error/error)
    constructor.

[`Error.prototype.name`](error/name)

:   Represents the name for the type of error. For
    `Error.prototype.name`, the initial value is `"Error"`. Subclasses
    like [`TypeError`](typeerror) and [`SyntaxError`](syntaxerror)
    provide their own `name` properties.

[`Error.prototype.stack`](error/stack) [Non-standard]

:   A non-standard property for a stack trace.

These properties are own properties of each `Error` instance.

[`cause`](error/cause)

:   Error cause indicating the reason why the current error is thrown
    --- usually another caught error. For user-created `Error` objects,
    this is the value provided as the `cause` property of the
    constructor\'s second argument.

[`columnNumber`](error/columnnumber) [Non-standard]

:   A non-standard Mozilla property for the column number in the line
    that raised this error.

[`fileName`](error/filename) [Non-standard]

:   A non-standard Mozilla property for the path to the file that raised
    this error.

[`lineNumber`](error/linenumber) [Non-standard]

:   A non-standard Mozilla property for the line number in the file that
    raised this error.

[`message`](error/message)

:   Error message. For user-created `Error` objects, this is the string
    provided as the constructor\'s first argument.



 
Instance methods 
----------------

 

[`Error.prototype.toString()`](error/tostring)

:   Returns a string representing the specified object. Overrides the
    [`Object.prototype.toString()`](object/tostring) method.



 
Examples
--------


 
### Throwing a generic error 

 
Usually you create an `Error` object with the intention of raising it
using the [`throw`](../statements/throw) keyword. You can handle the
error using the [`try...catch`](../statements/try...catch) construct:

 
 
[js]


```js
try {
  throw new Error("Whoops!");
} catch (e) {
  console.error(`${e.name}: ${e.message}`);
}
```




 
### Handling a specific error type 

 
You can choose to handle only specific error types by testing the error
type with the [`instanceof`](../operators/instanceof) keyword:

 
 
[js]


```js
try {
  foo.bar();
} catch (e) {
  if (e instanceof EvalError) {
    console.error(`${e.name}: ${e.message}`);
  } else if (e instanceof RangeError) {
    console.error(`${e.name}: ${e.message}`);
  }
  // etc.
  else {
    // If none of our cases matched leave the Error unhandled
    throw e;
  }
}
```




 
### Differentiate between similar errors 

 
Sometimes a block of code can fail for reasons that require different
handling, but which throw very similar errors (i.e. with the same type
and message).

If you don\'t have control over the original errors that are thrown, one
option is to catch them and throw new `Error` objects that have more
specific messages. The original error should be passed to the new
`Error` in the constructor\'s [`options`](error/error#options) parameter
as its `cause` property. This ensures that the original error and stack
trace are available to higher-level try/catch blocks.

The example below shows this for two methods that would otherwise fail
with similar errors (`doFailSomeWay()` and `doFailAnotherWay()`):

 
 
[js]


```js
function doWork() {
  try {
    doFailSomeWay();
  } catch (err) {
    throw new Error("Failed in some way", { cause: err });
  }
  try {
    doFailAnotherWay();
  } catch (err) {
    throw new Error("Failed in another way", { cause: err });
  }
}

try {
  doWork();
} catch (err) {
  switch (err.message) {
    case "Failed in some way":
      handleFailSomeWay(err.cause);
      break;
    case "Failed in another way":
      handleFailAnotherWay(err.cause);
      break;
  }
}
```


 
**Note:** If you are making a library, you should prefer to use error
cause to discriminate between different errors emitted --- rather than
asking your consumers to parse the error message. See the [error cause
page](error/cause#providing_structured_data_as_the_error_cause) for an
example.


[Custom error types](#custom_error_types) can also use the `cause`
property, provided the subclasses\' constructor passes the `options`
parameter when calling `super()`. The `Error()` base class constructor
will read `options.cause` and define the `cause` property on the new
error instance.

 
 
[js]


```js
class MyError extends Error {
  constructor(message, options) {
    // Need to pass `options` as the second parameter to install the "cause" property.
    super(message, options);
  }
}

console.log(new MyError("test", { cause: new Error("cause") }).cause);
// Error: cause
```




 
### Custom error types 

 
You might want to define your own error types deriving from `Error` to
be able to `throw new MyError()` and use `instanceof MyError` to check
the kind of error in the exception handler. This results in cleaner and
more consistent error handling code.

See [\"What\'s a good way to extend Error in
JavaScript?\"](https://stackoverflow.com/questions/1382107/whats-a-good-way-to-extend-error-in-javascript)
on StackOverflow for an in-depth discussion.

 
**Warning:** Builtin subclassing cannot be reliably transpiled to
pre-ES6 code, because there\'s no way to construct the base class with a
particular `new.target` without
[`Reflect.construct()`](reflect/construct). You need [additional
configuration](https://github.com/loganfsmyth/babel-plugin-transform-builtin-extend)
or manually call
[`Object.setPrototypeOf(this, CustomError.prototype)`](object/setprototypeof)
at the end of the constructor; otherwise, the constructed instance will
not be a `CustomError` instance. See [the TypeScript
FAQ](https://github.com/microsoft/TypeScript/wiki/FAQ#why-doesnt-extending-built-ins-like-error-array-and-map-work)
for more information.


 
**Note:** Some browsers include the `CustomError` constructor in the
stack trace when using ES2015 classes.


 
 
[js]


```js
class CustomError extends Error {
  constructor(foo = "bar", ...params) {
    // Pass remaining arguments (including vendor specific ones) to parent constructor
    super(...params);

    // Maintains proper stack trace for where our error was thrown (only available on V8)
    if (Error.captureStackTrace) {
      Error.captureStackTrace(this, CustomError);
    }

    this.name = "CustomError";
    // Custom debugging information
    this.foo = foo;
    this.date = new Date();
  }
}

try {
  throw new CustomError("baz", "bazMessage");
} catch (e) {
  console.error(e.name); // CustomError
  console.error(e.foo); // baz
  console.error(e.message); // bazMessage
  console.error(e.stack); // stacktrace
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-error-objects]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-error-objects)

  -----------------------------------------------------------------------------------------------------------


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

`Error`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`Error`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

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

`columnNumber`

No

No

1

No

No

No

4

No

No

No

No

No

No

`fileName`

No

No

1

No

No

No

4

No

No

No

No

No

No

`lineNumber`

No

No

1

No

No

No

4

No

No

No

No

No

No

`message`

1

12

1

5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`name`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`serializable_object`

77

79

103\[\"Version 103 serialized properties: `name`, `message`, `cause`,
`fileName`, `lineNumber` and `columnNumber`.\", \"Version 104 adds
serialization of `stack` in the main thread
([`window.postMessage()`](https://developer.mozilla.org/docs/Web/API/Window/postMessage)
and
[`structuredClone()`](https://developer.mozilla.org/docs/Web/API/structuredClone)).\",
\"Version 110 adds serialization of `stack` in workers
([`worker.postMessage()`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage)
and
[`structuredClone()`](https://developer.mozilla.org/docs/Web/API/structuredClone)).\"\]

64

No

77

103\[\"Version 103 serialized properties: `name`, `message`, `cause`,
`fileName`, `lineNumber` and `columnNumber`.\", \"Version 104 adds
serialization of `stack` in the main thread
([`window.postMessage()`](https://developer.mozilla.org/docs/Web/API/Window/postMessage)
and
[`structuredClone()`](https://developer.mozilla.org/docs/Web/API/structuredClone)).\",
\"Version 110 adds serialization of `stack` in workers
([`worker.postMessage()`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage)
and
[`structuredClone()`](https://developer.mozilla.org/docs/Web/API/structuredClone)).\"\]

55

No

12.0

77

No

No

`stack`

3

12

1

10.5

6

18

4

11

6

1.0

≤37

1.0

0.10.0

`toString`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `Error` with `cause` support in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-error)
-   [`throw`](../statements/throw)
-   [`try...catch`](../statements/try...catch)
-   [Stack trace API](https://v8.dev/docs/stack-trace-api) in the V8
    docs



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error>

