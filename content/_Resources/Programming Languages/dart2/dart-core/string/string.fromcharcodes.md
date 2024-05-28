[dart:core](../../dart-core/dart-core-library){._links-link}

String.fromCharCodes constructor
================================

::: {.section .multi-line-signature}
String.fromCharCodes(

1.  [Iterable](../iterable-class)\<[int](../int-class)\> charCodes,
2.  \[[int](../int-class) start = 0,
3.  [int](../int-class)? end\]

)
:::

Allocates a new string containing the specified `charCodes`.

The `charCodes` can be both UTF-16 code units and runes. If a char-code
value is 16-bit, it is used as a code unit:

``` {.language-dart data-language="dart"}
final string = String.fromCharCodes([68]);
print(string); // D
```

If a char-code value is greater than 16-bits, it is decomposed into a
surrogate pair:

``` {.language-dart data-language="dart"}
final clef = String.fromCharCodes([0x1D11E]);
clef.codeUnitAt(0); // 0xD834
clef.codeUnitAt(1); // 0xDD1E
```

If `start` and `end` are provided, only the values of `charCodes` at
positions from `start` to, but not including, `end`, are used. The
`start` and `end` values must satisfy
`0 <= start <= end <= charCodes.length`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory String.fromCharCodes(Iterable<int> charCodes,
    [int start = 0, int? end]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/String.fromCharCodes.html>
:::
