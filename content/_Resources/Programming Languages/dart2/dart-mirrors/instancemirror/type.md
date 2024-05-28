[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

type property
=============

::: {#getter .section .multi-line-signature}
[ClassMirror](../classmirror-class) type
:::

A mirror on the type of the reflectee.

Returns a mirror on the actual class of the reflectee. The class of the
reflectee may differ from the object returned by invoking
[runtimeType](../../dart-core/object/runtimetype) on the reflectee.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ClassMirror get type;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/InstanceMirror/type.html>
:::
