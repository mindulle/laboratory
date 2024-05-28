[dart:async](../../dart-async/dart-async-library){._links-link}

addError method
===============

::: {.section .multi-line-signature}
void addError(

1.  [Object](../../dart-core/object-class) error,
2.  \[[StackTrace](../../dart-core/stacktrace-class)? stackTrace\]

)

::: {.features}
override
:::
:::

Sends or enqueues an error event.

Listeners receive this event at a later microtask. This behavior can be
overridden by using `sync` controllers. Note, however, that sync
controllers have to satisfy the preconditions mentioned in the
documentation of the constructors.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addError(Object error, [StackTrace? stackTrace]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/addError.html>
:::
