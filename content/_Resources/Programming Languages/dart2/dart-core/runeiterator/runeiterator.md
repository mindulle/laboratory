[dart:core](../../dart-core/dart-core-library){._links-link}

RuneIterator constructor
========================

::: {.section .multi-line-signature}
RuneIterator(

1.  [String](../string-class) string

)
:::

Create an iterator positioned at the beginning of the string.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RuneIterator(String string)
    : this.string = string,
      _position = 0,
      _nextPosition = 0;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/RuneIterator.html>
:::
