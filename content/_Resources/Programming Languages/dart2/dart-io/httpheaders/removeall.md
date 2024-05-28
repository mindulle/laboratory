[dart:io](../../dart-io/dart-io-library){._links-link}

removeAll method
================

::: {.section .multi-line-signature}
void removeAll(

1.  [String](../../dart-core/string-class) name

)
:::

Removes all values for the specified header name.

Some headers have system supplied values which cannot be removed. All
other values for `name` are removed. If there are no remaining values
for `name`, the header is no longer considered present.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeAll(String name);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/removeAll.html>
:::
