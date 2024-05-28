[dart:core](../../dart-core/dart-core-library){._links-link}

isAtSameMomentAs method
=======================

::: {.section .multi-line-signature}
[bool](../bool-class) isAtSameMomentAs(

1.  [DateTime](../datetime-class) other

)
:::

Returns true if [this](../datetime-class) occurs at the same moment as
`other`.

The comparison is independent of whether the time is in UTC or in the
local time zone.

``` {.language-dart data-language="dart"}
final now = DateTime.now();
final later = now.add(const Duration(seconds: 5));
print(!later.isAtSameMomentAs(now)); // true
print(now.isAtSameMomentAs(now)); // true

// This relation stays the same, even when changing timezones.
print(!later.isAtSameMomentAs(now.toUtc())); // true
print(!later.toUtc().isAtSameMomentAs(now)); // true

print(now.toUtc().isAtSameMomentAs(now)); // true
print(now.isAtSameMomentAs(now.toUtc())); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool isAtSameMomentAs(DateTime other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/isAtSameMomentAs.html>
:::
