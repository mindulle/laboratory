[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

reflectClass function
=====================

::: {.section .multi-line-signature}
[ClassMirror](classmirror-class) reflectClass(

1.  [Type](../dart-core/type-class) key

)
:::

Reflects a class declaration.

Let *C* be the original class declaration of the class represented by
`key`. This function returns a [ClassMirror](classmirror-class)
reflecting *C*.

If `key` is not an instance of [Type](../dart-core/type-class), then
this function throws an
[ArgumentError](../dart-core/argumenterror-class). If `key` is the Type
for dynamic or a function typedef, throws an
[ArgumentError](../dart-core/argumenterror-class).

Note that since one cannot obtain a [Type](../dart-core/type-class)
object from another isolate, this function can only be used to obtain
class mirrors on classes of the current isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external ClassMirror reflectClass(Type key);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/reflectClass.html>
:::
