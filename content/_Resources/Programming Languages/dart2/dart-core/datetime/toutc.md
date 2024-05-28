[dart:core](../../dart-core/dart-core-library){._links-link}

toUtc method
============

::: {.section .multi-line-signature}
[DateTime](../datetime-class) toUtc()
:::

Returns this DateTime value in the UTC time zone.

Returns [this](../datetime-class) if it is already in UTC. Otherwise
this method is equivalent to:

``` {.language-dart data-language="dart"}
DateTime.fromMicrosecondsSinceEpoch(microsecondsSinceEpoch,
                                    isUtc: true)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DateTime toUtc() {
  if (isUtc) return this;
  return DateTime._withValue(_value, isUtc: true);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/toUtc.html>
:::
