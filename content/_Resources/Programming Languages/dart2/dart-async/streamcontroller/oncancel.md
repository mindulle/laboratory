[dart:async](../../dart-async/dart-async-library){._links-link}

onCancel property
=================

::: {.section .multi-line-signature}
([FutureOr](../futureor-class)\<void\> Function?()?) onCancel

::: {.features}
read / write
:::
:::

The callback which is called when the stream is canceled.

May be set to `null`, in which case no callback will happen.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
abstract FutureOr<void> Function()? onCancel;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/onCancel.html>
:::
