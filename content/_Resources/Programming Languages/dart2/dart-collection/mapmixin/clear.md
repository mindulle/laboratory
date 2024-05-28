[dart:collection](../../dart-collection/dart-collection-library){._links-link}

clear method
============

::: {.section .multi-line-signature}
void clear()

::: {.features}
override
:::
:::

Removes all entries from the map.

After this, the map is empty.

``` {.language-dart data-language="dart"}
final planets = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Earth'};
planets.clear(); // {}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void clear();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapMixin/clear.html>
:::
