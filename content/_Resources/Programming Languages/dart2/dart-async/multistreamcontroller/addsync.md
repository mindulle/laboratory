[dart:async](../../dart-async/dart-async-library){._links-link}

addSync method
==============

::: {.section .multi-line-signature}
void addSync(

1.  T value

)
:::

Adds and delivers an event.

Adds an event like [add](../streamcontroller/add) and attempts to
deliver it immediately. Delivery can be delayed if other previously
added events are still pending delivery, if the subscription is paused,
or if the subscription isn\'t listening yet.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addSync(T value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/MultiStreamController/addSync.html>
:::
