[dart:core](../../dart-core/dart-core-library){._links-link}

DateTime.fromMicrosecondsSinceEpoch constructor
===============================================

::: {.section .multi-line-signature}
DateTime.fromMicrosecondsSinceEpoch(

1.  [int](../int-class) microsecondsSinceEpoch,
2.  {[bool](../bool-class) isUtc = false}

)
:::

Constructs a new [DateTime](../datetime-class) instance with the given
`microsecondsSinceEpoch`.

If `isUtc` is false, then the date is in the local time zone.

The constructed [DateTime](../datetime-class) represents
1970-01-01T00:00:00Z + `microsecondsSinceEpoch` us in the given time
zone (local or UTC).

``` {.language-dart data-language="dart"}
final newYearsEve =
    DateTime.fromMicrosecondsSinceEpoch(1640901600000000, isUtc:true);
print(newYearsEve); // 2021-12-31 19:30:00.000Z
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external DateTime.fromMicrosecondsSinceEpoch(int microsecondsSinceEpoch,
    {bool isUtc = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/DateTime.fromMicrosecondsSinceEpoch.html>
:::
