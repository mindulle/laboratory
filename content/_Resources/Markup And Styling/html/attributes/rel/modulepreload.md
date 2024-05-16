rel=modulepreload
=================

The `modulepreload` keyword, for the [`rel`](../rel) attribute of the
[`<link>`](../../element/link) element, provides a declarative way to
preemptively fetch a [module
script](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules),
parse and compile it, and store it in the document\'s module map for
later execution.

Preloading allows modules and their dependencies to be downloaded early,
and can also significantly reduce the overall download and processing
time. This is because it allows pages to fetch modules in parallel,
instead of sequentially as each module is processed and its dependencies
are discovered. Note however that you can\'t just preload everything!
What you choose to preload must be balanced against other operations
that might then be starved, adversely affecting user experience.

Links with `rel="modulepreload"` are similar to those with
[`rel="preload"`](preload). The main difference is that `preload` just
downloads the file and stores it in the cache, while `modulepreload`
gets the module, parses and compiles it, and puts the results into the
module map so that it is ready to execute.

When using `modulepreload` the fetch request mode is always
[`cors`](https://developer.mozilla.org/en-US/docs/Web/API/Request/mode#cors),
and the [`crossorigin`](../crossorigin) property is used to determine
the request [credential
mode](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials).
If `crossorigin` is set to [`anonymous`](../crossorigin#anonymous) or
[`""`](../crossorigin#sect1) (default), then the credentials mode is
[`same-origin`](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials#same-origin),
and user credentials such as cookies and authentication are only sent
for requests with the `same-origin`. If `crossorigin` is set to
[`use-credentials`](../crossorigin#use-credentials) then the credentials
mode is
[`include`](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials#include),
and user credentials for both single- and cross-origin requests.

The [`as`](../../element/link#as) attribute is optional for links with
`rel="modulepreload"`, and defaults to `"script"`. It can be set to
`"script"` or any script-like destination, such as `"audioworklet"`,
`"paintworklet"`, `"serviceworker"`, `"sharedworker"`, or `"worker"`. An
[`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event/Event)
named \"error\" is fired on the element if any other destination is
used.

A browser *may* additionally also choose to automatically fetch any
dependencies of the module resource. Note however that this is a
browser-specific optimization --- the only approach to ensure that all
browsers will try to preload a module\'s dependencies is to individually
specify them! Further, the events named `load` or `error` fire
immediately following success or failure of loading the *specified*
resources. If dependencies are automatically fetched, no additional
events are fired in the main thread (although you might monitor
additional requests in a service worker or on the server).

Examples
--------

Consider the
[basic-modules](https://github.com/mdn/js-examples/tree/master/module-examples/basic-modules)
example ([live
version](https://mdn.github.io/js-examples/module-examples/basic-modules/)),
introduced in the [JavaScript
modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#basic_example_structure)
guide.

This has a file structure as shown below, consisting of the top level
module `main.js`, which statically imports two dependency modules
`modules/canvas.js` and `modules/square.js` using the [`import`
statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import).

```text
index.html
main.js
modules/
    canvas.js
    square.js
```

The HTML for the example below shows how `main.js` is fetched in a
`<script>` element. Only after `main.js` has loaded does the browser
discover and fetch the two dependency modules.

[html]

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>Basic JavaScript module example</title>
    <style>
      canvas {
        border: 1px solid black;
      }
    </style>
    <script type="module" src="main.js"></script>
  </head>
  <body></body>
</html>
```

The HTML below updates the example to use `<link>` elements with
`rel="modulepreload"` for the main file and each of the dependency
modules. This is much faster because the three modules all start
downloading asynchronously and in parallel before they are needed. By
the time `main.js` has been parsed and its dependencies are known, they
have already been fetched and downloaded.

[html]

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>Basic JavaScript module example</title>
    <link rel="modulepreload" href="main.js" />
    <link rel="modulepreload" href="modules/canvas.js" />
    <link rel="modulepreload" href="modules/square.js" />
    <style>
      canvas {
        border: 1px solid black;
      }
    </style>

    <script type="module" src="main.js"></script>
  </head>
  <body></body>
</html>
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  link-type-modulepreload]](https://html.spec.whatwg.org/multipage/links.html#link-type-modulepreload)

  --------------------------------------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`modulepreload`

66

≤79

115

No

53

No

66

66

115

47

No

9.0

See also
--------

- [Speculative
    loading](https://developer.mozilla.org/en-US/docs/Web/Performance/Speculative_loading)
    for a comparison of `<link rel="modulepreload">` and other similar
    performance improvement features.
- [Preloading
    modules](https://developer.chrome.com/blog/modulepreload)
    (developer.chrome.com)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel/modulepreload>>
