[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

Returns a string representation of (some of) the elements of `this`.

Elements are represented by their own `toString` results.

The default representation always contains the first three elements. If
there are less than a hundred elements in the iterable, it also contains
the last two elements.

If the resulting string isn\'t above 80 characters, more elements are
included from the start of the iterable.

The conversion may omit calling `toString` on some elements if they are
known to not occur in the output, and it may stop iterating after a
hundred elements.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() => IterableBase.iterableToShortString(this, '(', ')');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/toString.html>
:::
