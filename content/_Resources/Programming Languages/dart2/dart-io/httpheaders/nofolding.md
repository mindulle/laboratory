[dart:io](../../dart-io/dart-io-library){._links-link}

noFolding method
================

::: {.section .multi-line-signature}
void noFolding(

1.  [String](../../dart-core/string-class) name

)
:::

Disables folding for the header named `name` when sending the HTTP
header.

By default, multiple header values are folded into a single header line
by separating the values with commas.

The \'set-cookie\' header has folding disabled by default.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void noFolding(String name);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/noFolding.html>
:::
