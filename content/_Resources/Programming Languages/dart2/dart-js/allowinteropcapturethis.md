[dart:js](../dart-js/dart-js-library){._links-link}

allowInteropCaptureThis function
================================

::: {.section .multi-line-signature}
[Function](../dart-core/function-class) allowInteropCaptureThis(

1.  [Function](../dart-core/function-class) f

)
:::

Returns a wrapper around function `f` that can be called from JavaScript
using `package:js` JavaScript interop, passing JavaScript `this` as the
first argument.

See [allowInterop](allowinterop).

When called from Dart, `null` will be passed as the first argument.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Function allowInteropCaptureThis(Function f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/allowInteropCaptureThis.html>
:::
