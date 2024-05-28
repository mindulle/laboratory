dart:cli library
================

Utilities for building CLI apps.

Deprecation notice
------------------

The functionality of this library is incomplete and may be removed in a
later version. See [waitFor](waitfor){.deprecated} for details.

Functions
---------

[waitFor](waitfor){.deprecated}\<T\>([Future](../dart-async/future-class)\<T\>
future, {[Duration](../dart-core/duration-class)? timeout}) → T

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"This functionality is
incomplete and may be removed in a later version\")
:::

Suspends the stack, runs microtasks, and handles incoming events until
`future` completes.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-cli/dart-cli-library.html>
:::
