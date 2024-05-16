break
=====

 
The `break` statement terminates the current loop or [`switch`](switch)
statement and transfers program control to the statement following the
terminated statement. It can also be used to jump past a [labeled
statement](label) when used within that labeled statement.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
break;
break label;
```


[`label`](#label) [Optional]

:   Identifier associated with the label of the statement to break to.
    If the `break` statement is not nested within a loop or
    [`switch`](switch), then the label identifier is required.



 
Description
-----------

 
When `break;` is encountered, the program breaks out of the innermost
`switch` or
[looping](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements#iterations)
statement and continues executing the next statement after that.

When `break label;` is encountered, the program breaks out of the
statement labeled with `label` and continues executing the next
statement after that. The `break` statement needs to be nested within
the referenced label. The labeled statement can be any statement
(commonly a [block](block) statement); it does not have to be another
loop statement.

A `break` statement, with or without a following label, cannot be used
at the top level of a script, module, function\'s body, or [static
initialization block](../classes/static_initialization_blocks), even
when the function or class is further contained within a loop.



 
Examples
--------


 
### break in while loop 

 
The following function has a `break` statement that terminates the
[`while`](while) loop when `i` is 3, and then returns the value `3 * x`.

 
 
[js]


```js
function testBreak(x) {
  let i = 0;

  while (i < 6) {
    if (i === 3) {
      break;
    }
    i += 1;
  }

  return i * x;
}
```




 
### break in switch statements 

 
The following code has a `break` statement that terminates the
[`switch`](switch) statement when a case is matched and the
corresponding code has run.

 
 
[js]


```js
const food = "sushi";

switch (food) {
  case "sushi":
    console.log("Sushi is originally from Japan.");
    break;
  case "pizza":
    console.log("Pizza is originally from Italy.");
    break;
  default:
    console.log("I have never heard of that dish.");
    break;
}
```




 
### break in labeled blocks 

 
The following code uses `break` statements with labeled blocks. By using
`break outerBlock`, control is transferred to the end of the block
statement marked as `outerBlock`.

 
 
[js]


```js
outerBlock: {
  innerBlock: {
    console.log("1");
    break outerBlock; // breaks out of both innerBlock and outerBlock
    console.log(":-("); // skipped
  }
  console.log("2"); // skipped
}
```




 
### Unsyntactic break statements 

 
A `break` statement must be nested within any label it references. The
following code also uses `break` statements with labeled blocks, but
generates a syntax error because its `break` statement references
`block2` but it\'s not nested within `block2`.

 
 
[js]


```js
block1: {
  console.log("1");
  break block2; // SyntaxError: label not found
}

block2: {
  console.log("2");
}
```


Syntax errors are also generated in the following code examples which
use `break` statements within functions that are nested within a loop,
or labeled block that the `break` statements are intended to break out
of.

 
 
[js]


```js
function testBreak(x) {
  let i = 0;

  while (i < 6) {
    if (i === 3) {
      (() => {
        break;
      })();
    }
    i += 1;
  }

  return i * x;
}

testBreak(1); // SyntaxError: Illegal break statement
```


 
 
[js]


```js
block1: {
  console.log("1");
  (() => {
    break block1; // SyntaxError: Undefined label 'block1'
  })();
}
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-break-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-break-statement)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`break`

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

 
-   [`continue`](continue)
-   [label](label)
-   [`switch`](switch)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break>

