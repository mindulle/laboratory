[dart:io](../../dart-io/dart-io-library){._links-link}

clear method
============

::: {.section .multi-line-signature}
void clear()
:::

Removes all headers.

Some headers have system supplied values which cannot be removed. All
other header values are removed, and header names with not remaining
values are no longer considered present.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void clear();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/clear.html>
:::
