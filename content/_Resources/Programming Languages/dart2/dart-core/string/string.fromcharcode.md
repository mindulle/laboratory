[dart:core](../../dart-core/dart-core-library){._links-link}

String.fromCharCode constructor
===============================

::: {.section .multi-line-signature}
String.fromCharCode(

1.  [int](../int-class) charCode

)
:::

Allocates a new string containing the specified `charCode`.

If the `charCode` can be represented by a single UTF-16 code unit, the
new string contains a single code unit. Otherwise, the [length](length)
is 2 and the code units form a surrogate pair. See documentation for
[fromCharCodes](string.fromcharcodes).

Creating a [String](../string-class) with one half of a surrogate pair
is allowed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory String.fromCharCode(int charCode);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/String.fromCharCode.html>
:::
