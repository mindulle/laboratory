[dart:core](../../dart-core/dart-core-library){._links-link}

RangeError constructor
======================

::: {.section .multi-line-signature}
RangeError(

1.  dynamic message

)
:::

Create a new [RangeError](../rangeerror-class) with the given `message`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
RangeError(var message)
    : start = null,
      end = null,
      super(message);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError/RangeError.html>
:::
