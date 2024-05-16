do\...while
===========

 
The `do...while` statement creates a loop that executes a specified
statement until the test condition evaluates to false. The condition is
evaluated after executing the statement, resulting in the specified
statement executing at least once.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
do
  statement
while (condition);
```


[`statement`](#statement)

:   A statement that is executed at least once and is re-executed each
    time the condition evaluates to true. To execute multiple statements
    within the loop, use a [block](block) statement (`{ /* ... */ }`) to
    group those statements.

[`condition`](#condition)

:   An expression evaluated after each pass through the loop. If
    `condition` [evaluates to
    true](https://developer.mozilla.org/en-US/docs/Glossary/Truthy), the
    `statement` is re-executed. When `condition` [evaluates to
    false](https://developer.mozilla.org/en-US/docs/Glossary/Falsy),
    control passes to the statement following the `do...while`.

    Note: Use the [`break`](break) statement to stop a loop before
    `condition` evaluates to false.



 
Examples
--------


 
### Using `do...while` 

 
In the following example, the `do...while` loop iterates at least once
and reiterates until `i` is no longer less than 5.

 
 
[js]


```js
let result = "";
let i = 0;
do {
  i += 1;
  result += `${i}`;
} while (i > 0 && i < 5);
// Despite i === 0 this will still loop as it starts off without the test

console.log(result);
```




 
### Using an assignment as a condition 

 
In some cases, it can make sense to use an assignment as a condition,
such as this:

 
 
[js]


```js
do {
  // …
} while ((match = regexp.exec(str)));
```


But when you do, there are readability tradeoffs. The [`while`](while)
documentation has a [Using an assignment as a
condition](while#using_an_assignment_as_a_condition) section with our
recommendations.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-do-while-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-do-while-statement)

  -------------------------------------------------------------------------------------------------------------------------------------------------


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

`do...while`

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

 
-   [`while`](while)
-   [`for`](for)
-   [`break`](break)
-   [`continue`](continue)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while>

