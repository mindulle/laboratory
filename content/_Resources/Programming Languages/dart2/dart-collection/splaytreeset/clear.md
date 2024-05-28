[dart:collection](../../dart-collection/dart-collection-library){._links-link}

clear method
============

::: {.section .multi-line-signature}
void clear()

::: {.features}
override
:::
:::

Removes all elements from the set.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
characters.clear(); // {}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void clear() {
  _clear();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/clear.html>
:::
