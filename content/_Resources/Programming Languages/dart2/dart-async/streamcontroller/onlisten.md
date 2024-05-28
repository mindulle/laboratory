[dart:async](../../dart-async/dart-async-library){._links-link}

onListen property
=================

::: {.section .multi-line-signature}
(void Function?()?) onListen

::: {.features}
read / write
:::
:::

The callback which is called when the stream is listened to.

May be set to `null`, in which case no callback will happen.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
abstract void Function()? onListen;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/onListen.html>
:::
