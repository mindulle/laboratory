[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

KeyRange.bound constructor
==========================

::: {.section .multi-line-signature}
KeyRange.bound(

1.  dynamic lower,
2.  dynamic upper,
3.  \[[bool](../../dart-core/bool-class) lowerOpen = false,
4.  [bool](../../dart-core/bool-class) upperOpen = false\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory KeyRange.bound(/*Key*/ lower, /*Key*/ upper,
        [bool lowerOpen = false, bool upperOpen = false]) =>
    _KeyRangeFactoryProvider.createKeyRange_bound(
        lower, upper, lowerOpen, upperOpen);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/KeyRange/KeyRange.bound.html>
:::
