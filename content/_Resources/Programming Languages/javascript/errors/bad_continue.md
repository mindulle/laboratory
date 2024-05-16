SyntaxError: continue must be inside loop
=========================================


The JavaScript exception \"continue must be inside loop\" occurs when a
[`continue`](../statements/continue) statement is not inside a loop
statement.



Message
-------


```text
SyntaxError: Illegal continue statement: no surrounding iteration statement (V8-based)
SyntaxError: Illegal continue statement: 'label' does not denote an iteration statement (V8-based)
SyntaxError: continue must be inside loop (Firefox)
SyntaxError: 'continue' is only valid inside a loop statement. (Safari)
SyntaxError: Cannot continue to the label 'label' as it is not targeting a loop. (Safari)
```




Error type 
----------


[`SyntaxError`](../global_objects/syntaxerror).




What went wrong? 
----------------


[`continue`](../statements/continue) statements can be used to continue
a loop, and using them elsewhere is a syntax error. Alternatively, you
can provide a [label](../statements/label) to the `continue` statement
to continue any loop with that label --- however, if the label does not
reference a containing statement, another error [SyntaxError: label not
found](label_not_found) will be thrown, and if the label references a
statement that is not a loop, a syntax error is still thrown.




Examples
--------



### Using continue in callbacks 


If you want to proceed with the next iteration in a
[`forEach()`](../global_objects/array/foreach) loop, use
[`return`](../statements/return) instead, or convert it to a
[`for...of`](../statements/for...of) loop.



[js]


```js
array.forEach((value) => {
  if (value === 5) {
    continue; // SyntaxError: continue must be inside loop
  }
  // do something with value
});
```




[js]


```js
array.forEach((value) => {
  if (value === 5) {
    return;
  }
  // do something with value
});
```




[js]


```js
for (const value of array) {
  if (value === 5) {
    continue;
  }
  // do something with value
}
```





See also 
--------


-   [`continue`](../statements/continue)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_continue>

