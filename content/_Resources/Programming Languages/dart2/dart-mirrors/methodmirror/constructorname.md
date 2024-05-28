[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

constructorName property
========================

::: {#getter .section .multi-line-signature}
[Symbol](../../dart-core/symbol-class) constructorName
:::

The constructor name for named constructors and factory methods.

For unnamed constructors, this is the empty string. For
non-constructors, this is the empty string.

For example, `'bar'` is the constructor name for constructor `Foo.bar`
of type `Foo`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Symbol get constructorName;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MethodMirror/constructorName.html>
:::
