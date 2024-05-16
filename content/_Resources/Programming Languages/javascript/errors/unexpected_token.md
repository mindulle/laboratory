SyntaxError: Unexpected token
=============================

 
The JavaScript exceptions \"unexpected token\" occur when a specific
language construct was expected, but something else was provided. This
might be a simple typo.


 
Message
-------

 
```text
SyntaxError: expected expression, got "x"
SyntaxError: expected property name, got "x"
SyntaxError: expected target, got "x"
SyntaxError: expected rest argument name, got "x"
SyntaxError: expected closing parenthesis, got "x"
SyntaxError: expected '=>' after argument list, got "x"
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
A specific language construct was expected, but something else was
provided. This might be a simple typo.



 
Examples
--------


 
### Expression expected 

 
For example, when chaining expressions, trailing commas are not allowed.

 
 
[js]


```js
for (let i = 0; i < 5,; ++i) {
  console.log(i);
}
// Uncaught SyntaxError: expected expression, got ';'
```


Correct would be omitting the comma or adding another expression:

 
 
[js]


```js
for (let i = 0; i < 5; ++i) {
  console.log(i);
}
```




 
### Not enough parentheses 

 
Sometimes, you leave out parentheses around `if` statements:

 
 
[js]


```js
function round(n, upperBound, lowerBound) {
  if (n > upperBound) || (n < lowerBound) { // Not enough parenthese here!
    throw new Error(`Number ${n} is more than ${upperBound} or less than ${lowerBound}`);
  } else if (n < (upperBound + lowerBound) / 2) {
    return lowerBound;
  } else {
    return upperBound;
  }
} // SyntaxError: expected expression, got '||'
```


The parentheses may look correct at first, but note how the `||` is
outside the parentheses. Correct would be putting parentheses around the
`||`:

 
 
[js]


```js
function round(n, upperBound, lowerBound) {
  if ((n > upperBound) || (n < lowerBound)) {
    throw new Error(
      `Number ${n} is more than ${upperBound} or less than ${lowerBound}`,
    );
  } else if (n < (upperBound + lowerBound) / 2) {
    return lowerBound;
  } else {
    return upperBound;
  }
}
```




 
See also 
--------

 
-   [`SyntaxError`](../global_objects/syntaxerror)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unexpected_token>

