[dart:core](../../dart-core/dart-core-library){._links-link}

isAfter method
==============

::: {.section .multi-line-signature}
[bool](../bool-class) isAfter(

1.  [DateTime](../datetime-class) other

)
:::

Returns true if [this](../datetime-class) occurs after `other`.

The comparison is independent of whether the time is in UTC or in the
local time zone.

``` {.language-dart data-language="dart"}
final now = DateTime.now();
final later = now.add(const Duration(seconds: 5));
print(later.isAfter(now)); // true
print(!now.isBefore(now)); // true

// This relation stays the same, even when changing timezones.
print(later.isAfter(now.toUtc())); // true
print(later.toUtc().isAfter(now)); // true

print(!now.toUtc().isAfter(now)); // true
print(!now.isAfter(now.toUtc())); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool isAfter(DateTime other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/isAfter.html>
:::
