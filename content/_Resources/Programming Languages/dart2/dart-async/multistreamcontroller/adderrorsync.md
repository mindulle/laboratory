[dart:async](../../dart-async/dart-async-library){._links-link}

addErrorSync method
===================

::: {.section .multi-line-signature}
void addErrorSync(

1.  [Object](../../dart-core/object-class) error,
2.  \[[StackTrace](../../dart-core/stacktrace-class)? stackTrace\]

)
:::

Adds and delivers an error event.

Adds an error like [addError](../streamcontroller/adderror) and attempts
to deliver it immediately. Delivery can be delayed if other previously
added events are still pending delivery, if the subscription is paused,
or if the subscription isn\'t listening yet.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addErrorSync(Object error, [StackTrace? stackTrace]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/MultiStreamController/addErrorSync.html>
:::
