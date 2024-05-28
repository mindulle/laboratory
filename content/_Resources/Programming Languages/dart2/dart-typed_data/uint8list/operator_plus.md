[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

operator + method
=================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
operator +(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    other

)

::: {.features}
override
:::
:::

Returns a concatenation of this list and `other`.

If `other` is also a typed-data list, then the return list will be a
typed data list capable of holding both unsigned 8-bit integers and the
elements of `other`, otherwise it\'ll be a normal list of integers.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<int> operator +(List<int> other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Uint8List/operator_plus.html>
:::
