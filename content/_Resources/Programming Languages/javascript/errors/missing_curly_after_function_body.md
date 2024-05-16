SyntaxError: missing } after function body
==========================================

 
The JavaScript exception \"missing } after function body\" occurs when
there is a syntax mistake when creating a function somewhere. Check if
any closing curly braces or parenthesis are in the correct order.


 
Message
-------

 
```text
SyntaxError: missing } after function body (Firefox)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
There is a syntax mistake when creating a function somewhere. Also check
if any closing curly braces or parenthesis are in the correct order.
Indenting or formatting the code a bit nicer might also help you to see
through the jungle.



 
Examples
--------


 
### Forgotten closing curly bracket 

 
Oftentimes, there is a missing curly bracket in your function code:

 
 
[js]


```js
function charge() {
  if (sunny) {
    useSolarCells();
  } else {
    promptBikeRide();
}
```


Correct would be:

 
 
[js]


```js
function charge() {
  if (sunny) {
    useSolarCells();
  } else {
    promptBikeRide();
  }
}
```


It can be more obscure when using
[IIFEs](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) or other
constructs that use a lot of different parenthesis and curly braces, for
example.

 
 
[js]


```js
(function () {
  if (Math.random() < 0.01) {
    doSomething();
  }
)();
```


Oftentimes, indenting differently or double checking indentation helps
to spot these errors.

 
 
[js]


```js
(function () {
  if (Math.random() < 0.01) {
    doSomething();
  }
})();
```




 
See also 
--------

 
-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_curly_after_function_body>

