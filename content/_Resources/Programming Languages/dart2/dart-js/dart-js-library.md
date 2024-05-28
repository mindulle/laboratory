dart:js library
===============

Low-level support for interoperating with JavaScript.

You should usually use `package:js` instead of this library. For more
information, see the [JS interop page](https://dart.dev/web/js-interop).

This library provides access to JavaScript objects from Dart, allowing
Dart code to get and set properties, and call methods of JavaScript
objects and invoke JavaScript functions. The library takes care of
converting between Dart and JavaScript objects where possible, or
providing proxies if conversion isn\'t possible.

This library does not make Dart objects usable from JavaScript, their
methods and properties are not accessible, though it does allow Dart
functions to be passed into and called from JavaScript.

[JsObject](jsobject-class) is the core type and represents a proxy of a
JavaScript object. JsObject gives access to the underlying JavaScript
objects properties and methods. `JsObject`s can be acquired by calls to
JavaScript, or they can be created from proxies to JavaScript
constructors.

The top-level getter [context](context) provides a
[JsObject](jsobject-class) that represents the global object in
JavaScript, usually `window`.

The following example shows an alert dialog via a JavaScript call to the
global function `alert()`:

``` {.language-dart data-language="dart"}
import 'dart:js';

main() => context.callMethod('alert', ['Hello from Dart!']);
```

This example shows how to create a [JsObject](jsobject-class) from a
JavaScript constructor and access its properties:

``` {.language-dart data-language="dart"}
import 'dart:js';

main() {
  var object = JsObject(context['Object']);
  object['greeting'] = 'Hello';
  object['greet'] = (name) => "${object['greeting']} $name";
  var message = object.callMethod('greet', ['JavaScript']);
  context['console'].callMethod('log', [message]);
}
```

Proxying and automatic conversion
---------------------------------

When setting properties on a JsObject or passing arguments to a
Javascript method or function, Dart objects are automatically converted
or proxied to JavaScript objects. When accessing JavaScript properties,
or when a Dart closure is invoked from JavaScript, the JavaScript
objects are also converted to Dart.

Functions and closures are proxied in such a way that they are callable.
A Dart closure assigned to a JavaScript property is proxied by a
function in JavaScript. A JavaScript function accessed from Dart is
proxied by a [JsFunction](jsfunction-class), which has a
[JsFunction.apply](jsfunction/apply) method to invoke it.

The following types are transferred directly and not proxied:

-   Basic types: `null`, `bool`, `num`, `String`, `DateTime`
-   `TypedData`, including its subclasses like `Int32List`, but *not*
    `ByteBuffer`
-   When compiling for the web, also: `Blob`, `Event`, `ImageData`,
    `KeyRange`, `Node`, and `Window`.

Converting collections with JsObject.jsify() {#converting-collections-with-jsobjectjsify}
--------------------------------------------

To create a JavaScript collection from a Dart collection use the
[JsObject.jsify](jsobject/jsobject.jsify) constructor, which converts
Dart [Map](../dart-core/map-class)s and
[Iterable](../dart-core/iterable-class)s into JavaScript Objects and
Arrays.

The following expression creates a new JavaScript object with the
properties `a` and `b` defined:

``` {.language-dart data-language="dart"}
var jsMap = JsObject.jsify({'a': 1, 'b': 2});
```

This expression creates a JavaScript array:

``` {.language-dart data-language="dart"}
var jsArray = JsObject.jsify([1, 2, 3]);
```

Classes
-------

[JsArray](jsarray-class)\<E\>
:   A [List](../dart-core/list-class) that proxies a JavaScript array.

[JsFunction](jsfunction-class)
:   A proxy on a JavaScript Function object.

[JsObject](jsobject-class)
:   A proxy on a JavaScript object.

Properties
----------

[context](context) → [JsObject](jsobject-class)

::: {.features}
read-only
:::

The JavaScript global object, usually `window`.

Functions
---------

[allowInterop](allowinterop)\<F extends [Function](../dart-core/function-class)\>(F f) → F
:   Returns a wrapper around function `f` that can be called from
    JavaScript using `package:js` JavaScript interop.

[allowInteropCaptureThis](allowinteropcapturethis)([Function](../dart-core/function-class) f) → [Function](../dart-core/function-class)
:   Returns a wrapper around function `f` that can be called from
    JavaScript using `package:js` JavaScript interop, passing JavaScript
    `this` as the first argument.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/dart-js-library.html>
:::
