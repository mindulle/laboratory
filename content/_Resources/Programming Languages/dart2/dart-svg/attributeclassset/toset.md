[dart:svg](../../dart-svg/dart-svg-library){._links-link}

toSet method
============

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<[String](../../dart-core/string-class)\>
toSet()

::: {.features}
inherited
:::
:::

Creates a [Set](../../dart-core/set-class) with the same elements and
behavior as this `Set`.

The returned set behaves the same as this set with regard to adding and
removing elements. It initially contains the same elements. If this set
specifies an ordering of the elements, the returned set will have the
same order.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<String> toSet() => readClasses().toSet();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/toSet.html>
:::
