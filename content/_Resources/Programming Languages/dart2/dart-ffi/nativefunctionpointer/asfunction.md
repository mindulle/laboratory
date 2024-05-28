[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

asFunction\<@[DartRepresentationOf](../dartrepresentationof-class)(\'NF\') DF extends Function\> method
=======================================================================================================

::: {.section .multi-line-signature}
DF
asFunction\<@[DartRepresentationOf](../dartrepresentationof-class)(\'NF\')
DF extends Function\>(

1.  {[bool](../../dart-core/bool-class) isLeaf = false}

)
:::

Convert to Dart function, automatically marshalling the arguments and
return value.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external DF asFunction<@DartRepresentationOf('NF') DF extends Function>(
    {bool isLeaf: false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeFunctionPointer/asFunction.html>
:::
