[dart:html](../../dart-html/dart-html-library){._links-link}

FixedSizeListIterator\<T\> constructor
======================================

::: {.section .multi-line-signature}
FixedSizeListIterator\<T\>(

1.  [List](../../dart-core/list-class)\<T\> array

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
FixedSizeListIterator(List<T> array)
    : _array = array,
      _position = -1,
      _length = array.length;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FixedSizeListIterator/FixedSizeListIterator.html>
:::
