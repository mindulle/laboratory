[dart:core](../../dart-core/dart-core-library){._links-link}

DateTime.fromMillisecondsSinceEpoch constructor
===============================================

::: {.section .multi-line-signature}
DateTime.fromMillisecondsSinceEpoch(

1.  [int](../int-class) millisecondsSinceEpoch,
2.  {[bool](../bool-class) isUtc = false}

)
:::

Constructs a new [DateTime](../datetime-class) instance with the given
`millisecondsSinceEpoch`.

If `isUtc` is false then the date is in the local time zone.

The constructed [DateTime](../datetime-class) represents
1970-01-01T00:00:00Z + `millisecondsSinceEpoch` ms in the given time
zone (local or UTC).

``` {.language-dart data-language="dart"}
final newYearsDay =
    DateTime.fromMillisecondsSinceEpoch(1640979000000, isUtc:true);
print(newYearsDay); // 2022-01-01 10:00:00.000Z
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external DateTime.fromMillisecondsSinceEpoch(int millisecondsSinceEpoch,
    {bool isUtc = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/DateTime.fromMillisecondsSinceEpoch.html>
:::
