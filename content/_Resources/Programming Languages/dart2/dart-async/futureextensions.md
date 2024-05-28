[dart:async](../dart-async/dart-async-library){._links-link}

FutureExtensions\<T\> extension
===============================

Convenience methods on futures.

Adds functionality to futures which makes it easier to write well-typed
asynchronous code.

on

:   -   [Future](future-class)\<T\>

Annotations

-   \@Since(\"2.12\")

Methods {#instance-methods}
-------

[ignore](futureextensions/ignore)() → void

::: {.features}
\@Since(\"2.14\")
:::

Completely ignores this future and its result.

[onError](futureextensions/onerror)\<E extends
[Object](../dart-core/object-class)\>([FutureOr](futureor-class)\<T\>
handleError(E error, [StackTrace](../dart-core/stacktrace-class)
stackTrace), {[bool](../dart-core/bool-class) test(E error)?}) →
[Future](future-class)\<T\>

Handles errors on this future.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/FutureExtensions.html>
:::
