[dart:core](../../dart-core/dart-core-library){._links-link}

operator + method
=================

::: {.section .multi-line-signature}
[List](../list-class)\<E\> operator +(

1.  [List](../list-class)\<E\> other

)
:::

Returns the concatenation of this list and `other`.

Returns a new list containing the elements of this list followed by the
elements of `other`.

The default behavior is to return a normal growable list. Some list
types may choose to return a list of the same type as themselves (see
[Uint8List.+](../../dart-typed_data/uint8list/operator_plus));

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<E> operator +(List<E> other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/operator_plus.html>
:::
