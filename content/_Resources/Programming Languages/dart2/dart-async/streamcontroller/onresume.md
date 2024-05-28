[dart:async](../../dart-async/dart-async-library){._links-link}

onResume property
=================

::: {.section .multi-line-signature}
(void Function?()?) onResume

::: {.features}
read / write
:::
:::

The callback which is called when the stream is resumed.

May be set to `null`, in which case no callback will happen.

Pause related callbacks are not supported on broadcast stream
controllers.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
abstract void Function()? onResume;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/onResume.html>
:::
