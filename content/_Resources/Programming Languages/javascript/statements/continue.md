continue
========

 
The `continue` statement terminates execution of the statements in the
current iteration of the current or labeled loop, and continues
execution of the loop with the next iteration.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
continue;
continue label;
```


[`label`](#label) [Optional]

:   Identifier associated with the label of the statement.



 
Description
-----------

 
In contrast to the [`break`](break) statement, `continue` does not
terminate the execution of the loop entirely, but instead:

-   In a [`while`](while) or [`do...while`](do...while) loop, it jumps
    back to the condition.
-   In a [`for`](for) loop, it jumps to the update expression.
-   In a [`for...in`](for...in), [`for...of`](for...of), or
    [`for await...of`](for-await...of) loop, it jumps to the next
    iteration.

The `continue` statement can include an optional label that allows the
program to jump to the next iteration of a labeled loop statement
instead of the innermost loop. In this case, the `continue` statement
needs to be nested within this labeled statement.

A `continue` statement, with or without a following label, cannot be
used at the top level of a script, module, function\'s body, or [static
initialization block](../classes/static_initialization_blocks), even
when the function or class is further contained within a loop.



 
Examples
--------


 
### Using continue with while 

 
The following example shows a [`while`](while) loop that has a
`continue` statement that executes when the value of `i` is 3. Thus, `n`
takes on the values 1, 3, 7, and 12.

 
 
[js]


```js
let i = 0;
let n = 0;

while (i < 5) {
  i++;

  if (i === 3) {
    continue;
  }

  n += i;
}
```




 
### Using continue with a label 

 
In the following example, a statement labeled `checkIAndJ` contains a
statement labeled `checkJ`. If `continue` is encountered, the program
continues at the top of the `checkJ` statement. Each time `continue` is
encountered, `checkJ` reiterates until its condition returns false. When
false is returned, the remainder of the `checkIAndJ` statement is
completed.

If `continue` had a label of `checkIAndJ`, the program would continue at
the top of the `checkIAndJ` statement.

 
 
[js]


```js
let i = 0;
let j = 8;

checkIAndJ: while (i < 4) {
  console.log(`i: ${i}`);
  i += 1;

  checkJ: while (j > 4) {
    console.log(`j: ${j}`);
    j -= 1;

    if (j % 2 === 0) continue checkJ;
    console.log(`${j} is odd.`);
  }
  console.log(`i = ${i}`);
  console.log(`j = ${j}`);
}
```


Output:

```text
i: 0

// start checkj
j: 8
7 is odd.
j: 7
j: 6
5 is odd.
j: 5
// end checkj

i = 1
j = 4

i: 1
i = 2
j = 4

i: 2
i = 3
j = 4

i: 3
i = 4
j = 4
```



 
### Unsyntactic continue statements 

 
`continue` cannot be used within loops across function boundaries.

 
 
[js]


```js
for (let i = 0; i < 10; i++) {
  (() => {
    continue; // SyntaxError: Illegal continue statement: no surrounding iteration statement
  })();
}
```


When referencing a label, the labeled statement must contain the
`continue` statement.

 
 
[js]


```js
label: for (let i = 0; i < 10; i++) {
  console.log(i);
}

for (let i = 0; i < 10; i++) {
  continue label; // SyntaxError: Undefined label 'label'
}
```


The labeled statement must be a loop.

 
 
[js]


```js
label: {
  for (let i = 0; i < 10; i++) {
    continue label; // SyntaxError: Illegal continue statement: 'label' does not denote an iteration statement
  }
}
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-continue-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-continue-statement)

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

`continue`

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

 
-   [`break`](break)
-   [label](label)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue>

