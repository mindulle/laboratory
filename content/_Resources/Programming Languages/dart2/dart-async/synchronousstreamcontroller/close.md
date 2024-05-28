[dart:async](../../dart-async/dart-async-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../future-class) close()

::: {.features}
override
:::
:::

Closes the controller\'s stream.

As [StreamController.close](../streamcontroller/close), but must not be
called while an event is being added by [add](add), [addError](adderror)
or [close](close).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/SynchronousStreamController/close.html>
:::
