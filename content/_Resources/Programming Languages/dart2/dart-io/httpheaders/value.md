[dart:io](../../dart-io/dart-io-library){._links-link}

value method
============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class)? value(

1.  [String](../../dart-core/string-class) name

)
:::

Convenience method for the value for a single valued header.

The value must not have more than one value.

Returns `null` if there is no header with the provided name.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? value(String name);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/value.html>
:::
