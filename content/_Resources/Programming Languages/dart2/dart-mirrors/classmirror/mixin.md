[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

mixin property
==============

::: {#getter .section .multi-line-signature}
[ClassMirror](../classmirror-class) mixin
:::

The mixin of this class.

If this class is the result of a mixin application of the form S with M,
returns a class mirror on M. Otherwise returns a class mirror on the
reflectee.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ClassMirror get mixin;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClassMirror/mixin.html>
:::
