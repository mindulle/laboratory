[dart:core](../../dart-core/dart-core-library){._links-link}

lastIndexOf method
==================

::: {.section .multi-line-signature}
[int](../int-class) lastIndexOf(

1.  [Pattern](../pattern-class) pattern,
2.  \[[int](../int-class)? start\]

)
:::

The starting position of the last match `pattern` in this string.

Finds a match of pattern by searching backward starting at `start`:

``` {.language-dart data-language="dart"}
const string = 'Dartisans';
print(string.lastIndexOf('a')); // 6
print(string.lastIndexOf(RegExp(r'a(r|n)'))); // 6
```

Returns -1 if `pattern` could not be found in this string.

``` {.language-dart data-language="dart"}
const string = 'Dartisans';
print(string.lastIndexOf(RegExp(r'DART'))); // -1
```

If `start` is omitted, search starts from the end of the string. If
supplied, `start` must be non-negative and not greater than
[length](length).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int lastIndexOf(Pattern pattern, [int? start]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/lastIndexOf.html>
:::
