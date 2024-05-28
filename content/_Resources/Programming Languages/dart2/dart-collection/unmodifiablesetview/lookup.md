[dart:collection](../../dart-collection/dart-collection-library){._links-link}

lookup method
=============

::: {.section .multi-line-signature}
E? lookup(

1.  [Object](../../dart-core/object-class)? element

)

::: {.features}
override
:::
:::

If an object equal to `object` is in the set, return it.

Checks whether `object` is in the set, like [contains](contains), and if
so, returns the object in the set, otherwise returns `null`.

If the equality relation used by the set is not identity, then the
returned object may not be *identical* to `object`. Some set
implementations may not be able to implement this method. If the
[contains](contains) method is computed, rather than being based on an
actual object instance, then there may not be a specific object instance
representing the set element.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
final containsB = characters.lookup('B');
print(containsB); // B
final containsD = characters.lookup('D');
print(containsD); // null
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E? lookup(Object? element) => _source.lookup(element);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableSetView/lookup.html>
:::
