[dart:core](../../dart-core/dart-core-library){._links-link}

value property
==============

::: {.section .multi-line-signature}
V value

::: {.features}
final
:::
:::

The value associated to [key](key) in the map.

``` {.language-dart data-language="dart"}
final map = {'theKey': 'theValue'};
var entry = map.entries.first;
print(entry.value); // theValue
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final V value;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/MapEntry/value.html>
:::
