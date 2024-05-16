import.meta
===========

 
The `import.meta` meta-property exposes context-specific metadata to a
JavaScript module. It contains information about the module, such as the
module\'s URL.


 
Syntax
------

 
 
 
[js]


```js
import.meta
```




 
### Value

 
The `import.meta` object is created by the host environment, as an
extensible
[`null`-prototype](../global_objects/object#null-prototype_objects)
object where all properties are writable, configurable, and enumerable.
The spec doesn\'t specify any properties to be defined on it, but hosts
usually implement the following properties:

[`url`](#url)

:   The full URL to the module, includes query parameters and/or hash
    (following the `?` or `#`). In browsers, this is either the URL from
    which the script was obtained (for external scripts), or the URL of
    the containing document (for inline scripts). In Node.js, this is
    the file path (including the `file://` protocol).

[`resolve`](import.meta/resolve)

:   Resolves a module specifier to a URL using the current module\'s URL
    as base.



 
Description
-----------

 
The `import.meta` syntax consists of the keyword `import`, a dot, and
the identifier `meta`. Because `import` is a [reserved
word](../lexical_grammar#reserved_words), not an identifier, this is not
a [property accessor](property_accessors), but a special expression
syntax.

The `import.meta` meta-property is available in JavaScript modules;
using `import.meta` outside of a module (including [direct
`eval()`](../global_objects/eval#direct_and_indirect_eval) within a
module) is a syntax error.



 
Examples
--------


 
### Passing query parameters 

 
Using query parameters in the `import` specifier allows module-specific
argument passing, which may be complementary to reading parameters from
the application-wide
[`window.location`](https://developer.mozilla.org/en-US/docs/Web/API/Window/location)
(or on Node.js, through `process.argv`). For example, with the following
HTML:

 
 
[html]


```html
<script type="module">
  import "./index.mjs?someURLInfo=5";
</script>
```


The `index.mjs` module is able to retrieve the `someURLInfo` parameter
through `import.meta`:

 
 
[js]


```js
// index.mjs
new URL(import.meta.url).searchParams.get("someURLInfo"); // 5
```


The same applies when a module imports another:

 
 
[js]


```js
// index.mjs
import "./index2.mjs?someURLInfo=5";

// index2.mjs
new URL(import.meta.url).searchParams.get("someURLInfo"); // 5
```


The ES module implementation in Node.js supports resolving module
specifiers containing query parameters (or the hash), as in the latter
example. However, you cannot use queries or hashes when the module is
specified through the CLI command (like `node index.mjs?someURLInfo=5`),
because the CLI entrypoint uses a more CommonJS-like resolution mode,
treating the path as a file path rather than a URL. To pass parameters
to the entrypoint module, use CLI arguments and read them through
`process.argv` instead (like `node index.mjs --someURLInfo=5`).



 
### Resolving a file relative to the current one 

 
In Node.js CommonJS modules, there\'s a `__dirname` variable that
contains the absolute path to the folder containing current module,
which is useful for resolving relative paths. However, ES modules cannot
have contextual variables except for `import.meta`. Therefore, to
resolve a relative file you can use `import.meta.url`. Note that this
uses URLs rather than filesystem paths.

Before (CommonJS):

 
 
[js]


```js
const fs = require("fs/promises");
const path = require("path");

const filePath = path.join(__dirname, "someFile.txt");
fs.readFile(filePath, "utf8").then(console.log);
```


After (ES modules):

 
 
[js]


```js
import fs from "node:fs/promises";

const fileURL = new URL("./someFile.txt", import.meta.url);
fs.readFile(fileURL, "utf8").then(console.log);
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# prod-ImportMeta]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-ImportMeta)

  [HTML Standard\
  [\#
  hostgetimportmetaproperties]](https://html.spec.whatwg.org/multipage/webappapis.html#hostgetimportmetaproperties)
  ---------------------------------------------------------------------------------------------------------------------------


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

`import.meta`

64

79

62

51

11.1

64

62

47

12

9.0

64

1.0

10.4.0

`resolve`

105

105

106

91

16.4

105

106

72

16.4

20.0

105

1.24

20.6.0Returns a URL object instead of a string.

 
See also 
--------

 
-   [`import`](../statements/import)
-   [`export`](../statements/export)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/import.meta>

