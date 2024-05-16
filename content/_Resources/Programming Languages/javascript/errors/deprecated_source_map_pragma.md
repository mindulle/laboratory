SyntaxError: Using //@ to indicate sourceURL pragmas is deprecated. Use //\# instead
====================================================================================


The JavaScript warning \"Using `//@` to indicate sourceURL pragmas is
deprecated. Use `//#` instead\" occurs when there is a deprecated source
map syntax in a JavaScript source.



Message
-------


```text
Warning: SyntaxError: Using //@ to indicate sourceURL pragmas is deprecated. Use //# instead

Warning: SyntaxError: Using //@ to indicate sourceMappingURL pragmas is deprecated. Use //# instead
```




Error type 
----------


A warning that a [`SyntaxError`](../global_objects/syntaxerror)
occurred. JavaScript execution won\'t be halted.




What went wrong? 
----------------


There is a deprecated source map syntax in a JavaScript source.

JavaScript sources are often combined and minified to make delivering
them from the server more efficient. With [source
maps](https://firefox-source-docs.mozilla.org/devtools-user/debugger/how_to/use_a_source_map/index.html),
the debugger can map the code being executed to the original source
files.

The source map specification changed the syntax due to a conflict with
IE whenever it was found in the page after `//@cc_on` was interpreted to
turn on conditional compilation in the IE JScript engine. The
[conditional compilation
comment](https://stackoverflow.com/questions/24473882/what-does-this-comment-cc-on-0-do-inside-an-if-statement-in-javascript)
in IE is a little known feature, but it broke source maps with
[jQuery](https://bugs.jquery.com/ticket/13274) and other libraries.




Examples
--------



### Deprecated syntax 


Syntax with the \"@\" sign is deprecated.



[js]


```js
//@ sourceMappingURL=http://example.com/path/to/your/sourcemap.map
```





### Standard syntax 


Use the \"\#\" sign instead.



[js]


```js
//# sourceMappingURL=http://example.com/path/to/your/sourcemap.map
```


Or, alternatively, you can set a
[`SourceMap`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/SourceMap)
header to your JavaScript file to avoid having a comment at all:



[http]


```http
SourceMap: /path/to/file.js.map
```





See also 
--------


-   [Use a source
    map](https://firefox-source-docs.mozilla.org/devtools-user/debugger/how_to/use_a_source_map/index.html)
    in the Firefox source docs
-   [Introduction to JavaScript source
    maps](https://developer.chrome.com/blog/sourcemaps/) on
    developer.chrome.com (2012)
-   [`SourceMap`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/SourceMap)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_source_map_pragma>

