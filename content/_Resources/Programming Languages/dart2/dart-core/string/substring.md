[dart:core](../../dart-core/dart-core-library){._links-link}

substring method
================

::: {.section .multi-line-signature}
[String](../string-class) substring(

1.  [int](../int-class) start,
2.  \[[int](../int-class)? end\]

)
:::

The substring of this string from `start`, inclusive, to `end`,
exclusive.

Example:

``` {.language-dart data-language="dart"}
const string = 'dartlang';
var result = string.substring(1); // 'artlang'
result = string.substring(1, 4); // 'art'
```

Both `start` and `end` must be non-negative and no greater than
[length](length); `end`, if provided, must be greater than or equal to
`start`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String substring(int start, [int? end]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/substring.html>
:::
