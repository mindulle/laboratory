[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

referent property
=================

::: {#getter .section .multi-line-signature}
[FunctionTypeMirror](../functiontypemirror-class) referent
:::

The defining type for this typedef.

If the type referred to by the reflectee is a function type *F*, the
result will be `FunctionTypeMirror` reflecting *F* which is abstract and
has an abstract method `call` whose signature corresponds to *F*. For
instance `void f(int)` is the referent for `typedef void f(int)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
FunctionTypeMirror get referent;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/TypedefMirror/referent.html>
:::
