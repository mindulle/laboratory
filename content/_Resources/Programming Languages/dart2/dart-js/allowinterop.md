[dart:js](../dart-js/dart-js-library){._links-link}

allowInterop\<F extends Function\> function
===========================================

::: {.section .multi-line-signature}
F allowInterop\<F extends Function\>(

1.  F f

)
:::

Returns a wrapper around function `f` that can be called from JavaScript
using `package:js` JavaScript interop.

The calling conventions in Dart2Js differ from JavaScript and so, by
default, it is not possible to call a Dart function directly. Wrapping
with `allowInterop` creates a function that can be called from
JavaScript or Dart. The semantics of the wrapped function are still more
strict than JavaScript, and the function will throw if called with too
many or too few arguments.

Calling this method repeatedly on a function will return the same
result.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external F allowInterop<F extends Function>(F f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/allowInterop.html>
:::
