[dart:core](../../dart-core/dart-core-library){._links-link}

indexOf method
==============

::: {.section .multi-line-signature}
[int](../int-class) indexOf(

1.  [Pattern](../pattern-class) pattern,
2.  \[[int](../int-class) start = 0\]

)
:::

Returns the position of the first match of `pattern` in this string,
starting at `start`, inclusive:

``` {.language-dart data-language="dart"}
const string = 'Dartisans';
print(string.indexOf('art')); // 1
print(string.indexOf(RegExp(r'[A-Z][a-z]'))); // 0
```

Returns -1 if no match is found:

``` {.language-dart data-language="dart"}
const string = 'Dartisans';
string.indexOf(RegExp(r'dart')); // -1
```

The `start` must be non-negative and not greater than [length](length).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int indexOf(Pattern pattern, [int start = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/indexOf.html>
:::
