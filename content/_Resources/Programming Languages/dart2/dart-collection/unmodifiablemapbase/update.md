[dart:collection](../../dart-collection/dart-collection-library){._links-link}

update method
=============

::: {.section .multi-line-signature}
V update(

1.  K key,
2.  V update(
    1.  V value

    ),
3.  {V ifAbsent( )?}

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
V update(K key, V update(V value), {V Function()? ifAbsent}) {
  throw UnsupportedError("Cannot modify unmodifiable map");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableMapBase/update.html>
:::
