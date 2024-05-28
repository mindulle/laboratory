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

Adds error to the controller\'s stream.

As [StreamController.addError](../streamcontroller/adderror), but must
not be called while an event is being added by [add](add),
[addError](adderror) or [close](close).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addError(Object error, [StackTrace? stackTrace]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/SynchronousStreamController/addError.html>
:::
