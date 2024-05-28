[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    bytes

)
:::

Appends `bytes` to the current contents of this builder.

Each value of `bytes` will be truncated to an 8-bit value in the range 0
.. 255.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(List<int> bytes);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/BytesBuilder/add.html>
:::
