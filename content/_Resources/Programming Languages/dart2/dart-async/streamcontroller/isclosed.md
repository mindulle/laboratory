[dart:async](../../dart-async/dart-async-library){._links-link}

isClosed property
=================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isClosed
:::

Whether the stream controller is closed for adding more events.

The controller becomes closed by calling the [close](close) method. New
events cannot be added, by calling [add](add) or [addError](adderror),
to a closed controller.

If the controller is closed, the \"done\" event might not have been
delivered yet, but it has been scheduled, and it is too late to add more
events.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isClosed;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/isClosed.html>
:::
