import()
========

 
The `import()` syntax, commonly called *dynamic import*, is a
function-like expression that allows loading an ECMAScript module
asynchronously and dynamically into a potentially non-module
environment.

Unlike the [declaration-style counterpart](../statements/import),
dynamic imports are only evaluated when needed, and permit greater
syntactic flexibility.


 
Syntax
------

 
 
 
[js]


```js
import(moduleName)
```


The `import()` call is a syntax that closely resembles a function call,
but `import` itself is a keyword, not a function. You cannot alias it
like `const myImport = import`, which will throw a
[`SyntaxError`](../global_objects/syntaxerror).



 
### Parameters

 

[`moduleName`](#modulename)

:   The module to import from. The evaluation of the specifier is
    host-specified, but always follows the same algorithm as static
    [import declarations](../statements/import).



 
### Return value 

 
Returns a promise which fulfills to a [module namespace
object](#module_namespace_object): an object containing all exports from
`moduleName`.

The evaluation of `import()` never synchronously throws an error.
`moduleName` is [coerced to a
string](../global_objects/string#string_coercion), and if coercion
throws, the promise is rejected with the thrown error.



 
Description
-----------

 
The import declaration syntax (`import something from "somewhere"`) is
static and will always result in the imported module being evaluated at
load time. Dynamic imports allow one to circumvent the syntactic
rigidity of import declarations and load a module conditionally or on
demand. The following are some reasons why you might need to use dynamic
import:

-   When importing statically significantly slows the loading of your
    code or increases your program\'s memory usage, and there is a low
    likelihood that you will need the code you are importing, or you
    will not need it until a later time.
-   When the module you are importing does not exist at load time.
-   When the import specifier string needs to be constructed
    dynamically. (Static import only supports static specifiers.)
-   When the module being imported has side effects, and you do not want
    those side effects unless some condition is true. (It is recommended
    not to have any side effects in a module, but you sometimes cannot
    control this in your module dependencies.)
-   When you are in a non-module environment (for example, `eval` or a
    script file).

Use dynamic import only when necessary. The static form is preferable
for loading initial dependencies, and can benefit more readily from
static analysis tools and [tree
shaking](https://developer.mozilla.org/en-US/docs/Glossary/Tree_shaking).

If your file is not run as a module (if it\'s referenced in an HTML
file, the script tag must have `type="module"`), you will not be able to
use static import declarations, but the asynchronous dynamic import
syntax will always be available, allowing you to import modules into
non-module environments.

Dynamic module import is not permitted in all execution contexts. For
example, `import()` can be used in the main thread, a shared worker, or
a dedicated worker, but will throw if called within a [service
worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)
or a
[worklet](https://developer.mozilla.org/en-US/docs/Web/API/Worklet).



 
### Module namespace object 

 
A *module namespace object* is an object that describes all exports from
a module. It is a static object that is created when the module is
evaluated. There are two ways to access the module namespace object of a
module: through a [namespace
import](../statements/import#namespace_import)
(`import * as name from moduleName`), or through the fulfillment value
of a dynamic import.

The module namespace object is a
[sealed](../global_objects/object/issealed) object with [`null`
prototype](../global_objects/object#null-prototype_objects). This means
all string keys of the object correspond to the exports of the module
and there are never extra keys. All keys are
[enumerable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
in lexicographic order (i.e. the default behavior of
[`Array.prototype.sort()`](../global_objects/array/sort#description)),
with the default export available as a key called `default`. In
addition, the module namespace object has a
[`@@toStringTag`](../global_objects/symbol/tostringtag) property with
the value `"Module"`, used in
[`Object.prototype.toString()`](../global_objects/object/tostring).

The string properties are non-configurable and writable when you use
[`Object.getOwnPropertyDescriptors()`](../global_objects/object/getownpropertydescriptors)
to get their descriptors. However, they are effectively read-only,
because you cannot re-assign a property to a new value. This behavior
mirrors the fact that static imports create \"[live
bindings](../statements/import#imported_values_can_only_be_modified_by_the_exporter)\"
--- the values can be re-assigned by the module exporting them, but not
by the module importing them. The writability of the properties reflects
the possibility of the values changing, because non-configurable and
non-writable properties must be constant. For example, you can re-assign
the exported value of a variable, and the new value can be observed in
the module namespace object.

Each module specifier corresponds to a unique module namespace object,
so the following is generally true:

 
 
[js]


```js
import * as mod from "/my-module.js";

import("/my-module.js").then((mod2) => {
  console.log(mod === mod2); // true
});
```


Except in one curious case: because a promise never fulfills to a
[thenable](../global_objects/promise#thenables), if the `my-module.js`
module exports a function called `then()`, that function will
automatically get called when the dynamic import\'s promise is
fulfilled, as part of the [promise
resolution](../global_objects/promise/promise#the_resolve_function)
process.

 
 
[js]


```js
// my-module.js
export function then(resolve) {
  console.log("then() called");
  resolve(1);
}
```


 
 
[js]


```js
// main.js
import * as mod from "/my-module.js";

import("/my-module.js").then((mod2) => {
  // Logs "then() called"
  console.log(mod === mod2); // false
});
```


 
**Warning:** Do not export a function called `then()` from a module.
This will cause the module to behave differently when imported
dynamically than when imported statically.




 
Examples
--------


 
### Import a module for its side effects only 

 
 
 
[js]


```js
(async () => {
  if (somethingIsTrue) {
    // import module for side effects
    await import("/modules/my-module.js");
  }
})();
```


If your project uses packages that export ESM, you can also import them
for side effects only. This will run the code in the package entry point
file (and any files it imports) only.



 
### Importing defaults 

 
You need to destructure and rename the \"default\" key from the returned
object.

 
 
[js]


```js
(async () => {
  if (somethingIsTrue) {
    const {
      default: myDefault,
      foo,
      bar,
    } = await import("/modules/my-module.js");
  }
})();
```




 
### Importing on-demand in response to user action 

 
This example shows how to load functionality on to a page based on a
user action, in this case a button click, and then call a function
within that module. This is not the only way to implement this
functionality. The `import()` function also supports `await`.

 
 
[js]


```js
const main = document.querySelector("main");
for (const link of document.querySelectorAll("nav > a")) {
  link.addEventListener("click", (e) => {
    e.preventDefault();

    import("/modules/my-module.js")
      .then((module) => {
        module.loadPageInto(main);
      })
      .catch((err) => {
        main.textContent = err.message;
      });
  });
}
```




 
### Importing different modules based on environment 

 
In processes such as server-side rendering, you may need to load
different logic on server or in browser because they interact with
different globals or modules (for example, browser code has access to
web APIs like `document` and `navigator`, while server code has access
to the server file system). You can do so through a conditional dynamic
import.

 
 
[js]


```js
let myModule;

if (typeof window === "undefined") {
  myModule = await import("module-used-on-server");
} else {
  myModule = await import("module-used-in-browser");
}
```




 
### Importing modules with a non-literal specifier 

 
Dynamic imports allow any expression as the module specifier, not
necessarily string literals.

Here, we load 10 modules, `/modules/module-0.js`,
`/modules/module-1.js`, etc., concurrently, and call the `load`
functions that each one exports.

 
 
[js]


```js
Promise.all(
  Array.from({ length: 10 }).map(
    (_, index) => import(`/modules/module-${index}.js`),
  ),
).then((modules) => modules.forEach((module) => module.load()));
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-import-calls]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-import-calls)

  ---------------------------------------------------------------------------------------------------------------------


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

`import`

63

79

67

50

11.1

63

67

46

11.3

8.0

63

1.0Bundled Deno applications (using \`deno compile\`) do not support
dynamic imports

13.2.0Dynamic `import` can be used in either CommonJS or ES module
files, to import either CommonJS or ES module files. See Node\'s
[ECMAScript Modules
documentation](https://nodejs.org/api/esm.html#esm_import_expressions)
for more details.

12.17.0--13.0.0Dynamic `import` can be used in either CommonJS or ES
module files, to import either CommonJS or ES module files. See Node\'s
[ECMAScript Modules
documentation](https://nodejs.org/api/esm.html#esm_import_expressions)
for more details.

`options_parameter`

91

91

No

No

15

91

No

No

15

16.0

91

1.17

17.5.016.15.0--17.0.0

16.14.0--16.15.0The second parameter no longer throws a parser error,
but the `--experimental-json-modules` flag is still needed to load JSON
modules.

`worker_support`

80

80

114

67

15

80

114

57

15

13.0

80

1.0

No

 
See also 
--------

 
-   [`import`](../statements/import)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/import>

