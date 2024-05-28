[dart:core](../../dart-core/dart-core-library){._links-link}

toLocal method
==============

::: {.section .multi-line-signature}
[DateTime](../datetime-class) toLocal()
:::

Returns this DateTime value in the local time zone.

Returns [this](../datetime-class) if it is already in the local time
zone. Otherwise this method is equivalent to:

``` {.language-dart data-language="dart"}
DateTime.fromMicrosecondsSinceEpoch(microsecondsSinceEpoch,
                                    isUtc: false)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DateTime toLocal() {
  if (isUtc) {
    return DateTime._withValue(_value, isUtc: false);
  }
  return this;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/toLocal.html>
:::
