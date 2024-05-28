Dart SDK
========

Welcome to the [Dart](https://dart.dev/) API reference documentation,
covering the [Dart core libraries](https://dart.dev/guides/libraries).
These include:

-   [dart:core](dart-core/dart-core-library): Core functionality such as
    strings, numbers, collections, errors, dates, and URIs.
-   [dart:html](dart-html/dart-html-library): DOM manipulation for web
    apps (available only to web apps).
-   [dart:io](dart-io/dart-io-library): I/O for non-web apps.

Except for `dart:core`, you must import a library before you can use it.
Here\'s an example of importing `dart:async` and `dart:math`:

``` {.language-dart data-language="dart"}
import 'dart:async';
import 'dart:math';
```

You can find more libraries using the [pub.dev site](https://pub.dev).

The main site for learning and using Dart is
[dart.dev](https://dart.dev). Check out these pages:

-   [Platforms](https://dart.dev/platforms)
-   [Language tour](https://dart.dev/guides/language/language-tour)
-   [Library tour](https://dart.dev/guides/libraries/library-tour)
-   [Sample code](https://dart.dev/samples)

This API reference is automatically generated from source code in the
[Dart SDK project](https://github.com/dart-lang/sdk). If you\'d like to
give feedback or edit this documentation, see
[Contributing](https://github.com/dart-lang/sdk/wiki/Contributing).

Libraries
---------

[dart:async](dart-async/dart-async-library)
:   Support for asynchronous programming, with classes such as Future
    and Stream.

[dart:collection](dart-collection/dart-collection-library)
:   Classes and utilities that supplement the collection support in
    dart:core.

[dart:convert](dart-convert/dart-convert-library)
:   Encoders and decoders for converting between different data
    representations, including JSON and UTF-8.

[dart:core](dart-core/dart-core-library)
:   Built-in types, collections, and other core functionality for every
    Dart program.

[dart:developer](dart-developer/dart-developer-library)
:   Interact with developer tools such as the debugger and inspector.

[dart:math](dart-math/dart-math-library)
:   Mathematical constants and functions, plus a random number
    generator.

[dart:typed\_data](dart-typed_data/dart-typed_data-library)
:   Lists that efficiently handle fixed sized data (for example,
    unsigned 8 byte integers) and SIMD numeric types.

[dart:cli](dart-cli/dart-cli-library){.deprecated}
:   Utilities for building CLI apps.

[dart:ffi](dart-ffi/dart-ffi-library)
:   Foreign Function Interface for interoperability with the C
    programming language.

[dart:io](dart-io/dart-io-library)
:   File, socket, HTTP, and other I/O support for non-web applications.

[dart:isolate](dart-isolate/dart-isolate-library)
:   Concurrent programming using *isolates*: independent workers that
    are similar to threads but don\'t share memory, communicating only
    via messages.

[dart:mirrors](dart-mirrors/dart-mirrors-library)
:   Basic reflection in Dart, with support for introspection and dynamic
    invocation.

[dart:html](dart-html/dart-html-library)
:   HTML elements and other resources for web-based applications that
    need to interact with the browser and the DOM (Document Object
    Model).

[dart:indexed\_db](dart-indexed_db/dart-indexed_db-library)
:   A client-side key-value store with support for indexes.

[dart:js](dart-js/dart-js-library)
:   Low-level support for interoperating with JavaScript.

[dart:js\_util](dart-js_util/dart-js_util-library)
:   Utility methods to manipulate `package:js` annotated JavaScript
    interop objects in cases where the name to call is not known at
    runtime.

[dart:svg](dart-svg/dart-svg-library)
:   Scalable Vector Graphics: Two-dimensional vector graphics with
    support for events and animation.

[dart:web\_audio](dart-web_audio/dart-web_audio-library)
:   High-fidelity audio programming in the browser.

[dart:web\_gl](dart-web_gl/dart-web_gl-library)
:   3D programming in the browser.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/index.html>
:::
