Error.prototype.stack
=====================

 
 
**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.


 
**Note:** The `stack` property is de facto implemented by all major
JavaScript engines, and [the JavaScript standards committee is looking
to standardize it](https://github.com/tc39/proposal-error-stacks). You
cannot rely on the precise content of the stack string due to
implementation inconsistencies, but you can generally assume it exists
and use it for debugging purposes.


The non-standard `stack` property of an [`Error`](../error) instance
offers a trace of which functions were called, in what order, from which
line and file, and with what arguments. The stack string proceeds from
the most recent calls to earlier ones, leading back to the original
global scope call.


 
Value
-----

 
A string.

Because the `stack` property is non-standard, implementations differ
about where it\'s installed.

-   In Firefox, it\'s an accessor property on `Error.prototype`.
-   In Chrome and Safari, it\'s a data property on each `Error`
    instance, with the descriptor:

 
Property attributes of `Error.prototype.stack`




Writable

yes

Enumerable

no

Configurable

yes

 
Description
-----------

 
Each JavaScript engine uses its own format for stack traces, but they
are fairly consistent in their high-level structure. Every
implementation uses a separate line in the stack to represent each
function call. The call that directly caused the error is placed at the
top, and the call that started the whole call chain is placed at the
bottom. Below are some examples of stack traces:

 
 
[js]


```js
function foo() {
  bar();
}

function bar() {
  baz();
}

function baz() {
  console.log(new Error().stack);
}

foo();
```


```text
#### JavaScriptCore
baz@filename.js:10:24
bar@filename.js:6:6
foo@filename.js:2:6
global code@filename.js:13:4

#### SpiderMonkey
baz@filename.js:10:15
bar@filename.js:6:3
foo@filename.js:2:3
@filename.js:13:1

#### V8
Error
    at baz (filename.js:10:15)
    at bar (filename.js:6:3)
    at foo (filename.js:2:3)
    at filename.js:13:1
```

Different engines set this value at different times. Most modern engines
set it when the [`Error`](../error) object is created. This means you
can get the full call stack information within a function using the
following:

 
 
[js]


```js
function foo() {
  console.log(new Error().stack);
}
```


Without having to throw an error and then catch it.

In V8, the non-standard `Error.captureStackTrace()`,
`Error.stackTraceLimit`, and `Error.prepareStackTrace()` APIs can be
used to customize the stack trace. Read the [Stack trace
API](https://v8.dev/docs/stack-trace-api) in the V8 docs for more
information.

Stack frames can be things other than explicit function calls, too. For
example, event listeners, timeout jobs, and promise handlers all begin
their own call chain. Source code within [`eval()`](../eval) and
[`Function`](../function) constructor calls also appear in the stack:

 
 
[js]


```js
console.log(new Function("return new Error('Function failed')")().stack);
console.log("====");
console.log(eval("new Error('eval failed')").stack);
```


```text
#### JavaScriptCore
anonymous@
global code@filename.js:1:65
====
eval code@
eval@[native code]
global code@filename.js:3:17

#### SpiderMonkey
anonymous@filename.js line 1 > Function:1:8
@filename.js:1:65

====
@filename.js line 3 > eval:1:1
@filename.js:3:13

#### V8
Error: Function failed
    at eval (eval at <anonymous> (filename.js:1:13), <anonymous>:1:8)
    at filename.js:1:65
====
Error: eval failed
    at eval (eval at <anonymous> (filename.js:3:13), <anonymous>:1:1)
    at filename.js:3:13
```

In Firefox, you can use the `//# sourceURL` directive to name an eval
source. See the Firefox [Debug eval
sources](https://firefox-source-docs.mozilla.org/devtools-user/debugger/how_to/debug_eval_sources/index.html)
docs and the [Naming `eval` Scripts with the `//# sourceURL`
Directive](https://fitzgeraldnick.com/2014/12/05/name-eval-scripts.html)
blog post for more details.



 
Examples
--------


 
### Using the stack property 

 
The following script demonstrates how to use the `stack` property to
output a stack trace into your browser window. You can use this to check
what your browser\'s stack structure looks like.

 
 
[js]


```js
function trace() {
  throw new Error("trace() failed");
}
function b() {
  trace();
}
function a() {
  b(3, 4, "\n\n", undefined, {});
}
try {
  a("first call, firstarg");
} catch (e) {
  document.getElementById("output").textContent = e.stack;
}
```


 




 
Specifications
--------------

 
Not part of any standard.



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

 
See also 
--------

 
-   [TraceKit](https://github.com/csnover/TraceKit/) on GitHub
-   [stacktrace.js](https://github.com/stacktracejs/stacktrace.js) on
    GitHub
-   [Stack trace API](https://v8.dev/docs/stack-trace-api) in the V8
    docs



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/stack>

