[dart:core](../../dart-core/dart-core-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../bool-class) operator ==(

1.  [Object](../object-class) other

)

::: {.features}
override
:::
:::

Returns true if `other` is a [DateTime](../datetime-class) at the same
moment and in the same time zone (UTC or local).

``` {.language-dart data-language="dart"}
final dDayUtc = DateTime.utc(1944, 6, 6);
final dDayLocal = dDayUtc.toLocal();

// These two dates are at the same moment, but are in different zones.
assert(dDayUtc != dDayLocal);
print(dDayUtc != dDayLocal); // true
```

See [isAtSameMomentAs](isatsamemomentas) for a comparison that compares
moments in time independently of their zones.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool operator ==(Object other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/operator_equals.html>
:::
