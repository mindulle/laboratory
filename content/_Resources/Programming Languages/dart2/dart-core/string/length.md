[dart:core](../../dart-core/dart-core-library){._links-link}

length property
===============

::: {#getter .section .multi-line-signature}
[int](../int-class) length
:::

The length of the string.

Returns the number of UTF-16 code units in this string. The number of
[runes](runes) might be fewer if the string contains characters outside
the Basic Multilingual Plane (plane 0):

``` {.language-dart data-language="dart"}
'Dart'.length;          // 4
'Dart'.runes.length;    // 4

var clef = '\u{1D11E}';
clef.length;            // 2
clef.runes.length;      // 1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get length;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/length.html>
:::
