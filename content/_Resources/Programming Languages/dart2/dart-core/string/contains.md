[dart:core](../../dart-core/dart-core-library){._links-link}

contains method
===============

::: {.section .multi-line-signature}
[bool](../bool-class) contains(

1.  [Pattern](../pattern-class) other,
2.  \[[int](../int-class) startIndex = 0\]

)
:::

Whether this string contains a match of `other`.

Example:

``` {.language-dart data-language="dart"}
const string = 'Dart strings';
final containsD = string.contains('D'); // true
final containsUpperCase = string.contains(RegExp(r'[A-Z]')); // true
```

If `startIndex` is provided, this method matches only at or after that
index:

``` {.language-dart data-language="dart"}
const string = 'Dart strings';
final containsD = string.contains(RegExp('D'), 0); // true
final caseSensitive = string.contains(RegExp(r'[A-Z]'), 1); // false
```

The `startIndex` must not be negative or greater than [length](length).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool contains(Pattern other, [int startIndex = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/contains.html>
:::
