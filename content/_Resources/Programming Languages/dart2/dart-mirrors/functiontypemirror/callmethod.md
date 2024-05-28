[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

callMethod property
===================

::: {#getter .section .multi-line-signature}
[MethodMirror](../methodmirror-class) callMethod
:::

A mirror on the `call` method for the reflectee.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// This is only here because in the past the VM did not implement a call
// method on closures.
MethodMirror get callMethod;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/FunctionTypeMirror/callMethod.html>
:::
