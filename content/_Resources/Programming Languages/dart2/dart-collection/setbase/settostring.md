[dart:collection](../../dart-collection/dart-collection-library){._links-link}

setToString method
==================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) setToString(

1.  [Set](../../dart-core/set-class) set

)
:::

Converts a [Set](../../dart-core/set-class) to a
[String](../../dart-core/string-class).

Converts `set` to a string by converting each element to a string (by
calling [Object.toString](../../dart-core/object/tostring)), joining
them with \", \", and wrapping the result in \"{\" and \"}\".

Handles circular references where converting one of the elements to a
string ends up converting `set` to a string again.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String setToString(Set set) =>
    IterableBase.iterableToFullString(set, '{', '}');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetBase/setToString.html>
:::
