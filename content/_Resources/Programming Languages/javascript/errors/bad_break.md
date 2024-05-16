SyntaxError: unlabeled break must be inside loop or switch
==========================================================


The JavaScript exception \"unlabeled break must be inside loop or
switch\" occurs when a [`break`](../statements/break) statement is not
inside a loop or a [`switch`](../statements/switch) statement.



Message
-------


```text
SyntaxError: Illegal break statement (V8-based)
SyntaxError: unlabeled break must be inside loop or switch (Firefox)
SyntaxError: 'break' is only valid inside a switch or loop statement. (Safari)
```




Error type 
----------


[`SyntaxError`](../global_objects/syntaxerror).




What went wrong? 
----------------


[`break`](../statements/break) statements can be used to exit a loop or
a `switch` statement, and using them elsewhere is a syntax error.
Alternatively, you can provide a [label](../statements/label) to the
`break` statement to break out of any statement with that label ---
however, if the label does not reference a containing statement, another
error [SyntaxError: label not found](label_not_found) will be thrown.




Examples
--------



### Unsyntactic break 


`break` cannot be used outside `switch` or loops.



[js]


```js
let score = 0;

function increment() {
  if (score === 100)
    break; // SyntaxError: unlabeled break must be inside loop or switch
  }
  score++;
}
```


Maybe instead of `break`, you intend to use
[`return`](../statements/return) to early-terminate a function.



[js]


```js
let score = 0;

function increment() {
  if (score === 100) {
    return;
  }
  score++;
}
```





### Using break in callbacks 


`break` cannot be used in callbacks, even if the callback is called from
a loop.



[js]


```js
let containingIndex = 0;
const matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

while (containingIndex < matrix.length) {
  matrix[containingIndex].forEach((value) => {
    if (value === 5) {
      break; // SyntaxError: unlabeled break must be inside loop or switch
    }
  });
  containingIndex++;
}
```


Instead, refactor the code so the `break` is used outside the callback.



[js]


```js
let containingIndex = 0;
const matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

outer: while (containingIndex < matrix.length) {
  for (const value of matrix[containingIndex]) {
    if (value === 5) {
      break outer;
    }
  }
  containingIndex++;
}
```




[js]


```js
let containingIndex = 0;
const matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

while (containingIndex < matrix.length) {
  if (matrix[containingIndex].includes(5)) {
    break;
  }
  containingIndex++;
}
```


There\'s no way to early-terminate a
[`forEach()`](../global_objects/array/foreach) loop. You can use
[`some()`](../global_objects/array/some) instead, or convert it to a
[`for...of`](../statements/for...of) loop.



[js]


```js
array.forEach((value) => {
  if (value === 5) {
    break; // SyntaxError: unlabeled break must be inside loop or switch
  }
  // do something with value
});
```




[js]


```js
array.some((value) => {
  if (value === 5) {
    return true;
  }
  // do something with value
  return false;
});
```




[js]


```js
for (const value of array) {
  if (value === 5) {
    break;
  }
  // do something with value
}
```





See also 
--------


-   [`break`](../statements/break)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_break>

