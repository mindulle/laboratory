[dart:core](../../dart-core/dart-core-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[String](../string-class) operator \[\](

1.  [int](../int-class) index

)
:::

The character (as a single-code-unit [String](../string-class)) at the
given `index`.

The returned string represents exactly one UTF-16 code unit, which may
be half of a surrogate pair. A single member of a surrogate pair is an
invalid UTF-16 string:

``` {.language-dart data-language="dart"}
var clef = '\u{1D11E}';
// These represent invalid UTF-16 strings.
clef[0].codeUnits;      // [0xD834]
clef[1].codeUnits;      // [0xDD1E]
```

This method is equivalent to
`String.fromCharCode(this.codeUnitAt(index))`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String operator [](int index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/operator_get.html>
:::
