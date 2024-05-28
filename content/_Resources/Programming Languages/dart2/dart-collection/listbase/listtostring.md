[dart:collection](../../dart-collection/dart-collection-library){._links-link}

listToString method
===================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) listToString(

1.  [List](../../dart-core/list-class) list

)
:::

Converts a [List](../../dart-core/list-class) to a
[String](../../dart-core/string-class).

Converts `list` to a string by converting each element to a string (by
calling [Object.toString](../../dart-core/object/tostring)), joining
them with \", \", and wrapping the result in `[` and `]`.

Handles circular references where converting one of the elements to a
string ends up converting `list` to a string again.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String listToString(List list) =>
    IterableBase.iterableToFullString(list, '[', ']');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListBase/listToString.html>
:::
