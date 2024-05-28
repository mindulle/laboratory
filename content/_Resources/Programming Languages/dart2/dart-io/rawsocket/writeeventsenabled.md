[dart:io](../../dart-io/dart-io-library){._links-link}

writeEventsEnabled property
===========================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) writeEventsEnabled

::: {.features}
read / write
:::
:::

Set or get, if the [RawSocket](../rawsocket-class) should listen for
[RawSocketEvent.write](../rawsocketevent/write-constant) events. Default
is `true`. This is a one-shot listener, and writeEventsEnabled must be
set to true again to receive another write event.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
abstract bool writeEventsEnabled;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocket/writeEventsEnabled.html>
:::
