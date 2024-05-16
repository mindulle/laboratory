SyntaxError: await is only valid in async functions, async generators and modules
=================================================================================


The JavaScript exception \"await is only valid in async functions, async
generators and modules\" occurs when an [`await`](../operators/await)
expression is used outside of [async
functions](../statements/async_function) or
[modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
or other async contexts.



Message
-------


```text
SyntaxError: await is only valid in async functions and the top level bodies of modules (V8-based)
SyntaxError: await is only valid in async functions, async generators and modules (Firefox)
SyntaxError: Unexpected identifier (Safari)
```




Error type 
----------


[`SyntaxError`](../global_objects/syntaxerror).




What went wrong? 
----------------


JavaScript execution is never blocking: an `await` can never block the
execution of the program. Instead, it pauses the execution of the
surrounding async task, while allowing other tasks to continue running.
Therefore, `await` cannot be used in sync tasks, such as functions,
generator functions, or top level of scripts. It is not always apparent
whether the current file is a script or a module --- see the [Modules
guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#top_level_await)
for more information.




Examples
--------



### Top-level await 


You cannot use `await` at the top level of a script:



[html]


```html
<script>
  await fetch("https://example.com");
  // SyntaxError: await is only valid in async functions, async generators and modules
</script>
```


Instead, make the script a module:



[html]


```html
<script type="module">
  await fetch("https://example.com");
</script>
```





### Async callbacks 


You cannot use `await` in a sync callback:



[js]


```js
urls.forEach((url) => {
  await fetch(url);
  // SyntaxError: await is only valid in async functions, async generators and modules
});
```


Instead, make the callback async. See more explanation in the [Using
promises
guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#composition).



[js]


```js
Promise.all(
  urls.map(async (url) => {
    await fetch(url);
  }),
);
```





See also 
--------


-   [`await`](../operators/await)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_await>

