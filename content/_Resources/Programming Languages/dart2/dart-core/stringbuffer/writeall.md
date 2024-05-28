[dart:core](../../dart-core/dart-core-library){._links-link}

writeAll method
===============

::: {.section .multi-line-signature}
void writeAll(

1.  [Iterable](../iterable-class) objects,
2.  \[[String](../string-class) separator = \"\"\]

)

::: {.features}
override
:::
:::

Writes all `objects` separated by `separator`.

Writes each individual object in `objects` in iteration order, and
writes `separator` between any two objects.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void writeAll(Iterable<dynamic> objects, [String separator = ""]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/StringBuffer/writeAll.html>
:::
