[dart:core](../../dart-core/dart-core-library){._links-link}

isBefore method
===============

::: {.section .multi-line-signature}
[bool](../bool-class) isBefore(

1.  [DateTime](../datetime-class) other

)
:::

Returns true if [this](../datetime-class) occurs before `other`.

The comparison is independent of whether the time is in UTC or in the
local time zone.

``` {.language-dart data-language="dart"}
final now = DateTime.now();
final earlier = now.subtract(const Duration(seconds: 5));
print(earlier.isBefore(now)); // true
print(!now.isBefore(now)); // true

// This relation stays the same, even when changing timezones.
print(earlier.isBefore(now.toUtc())); // true
print(earlier.toUtc().isBefore(now)); // true

print(!now.toUtc().isBefore(now)); // true
print(!now.isBefore(now.toUtc())); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool isBefore(DateTime other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/isBefore.html>
:::
