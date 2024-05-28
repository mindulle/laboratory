[dart:io](../../dart-io/dart-io-library){._links-link}

CompressionOptions constructor
==============================

::: {.section .multi-line-signature}
const CompressionOptions(

1.  {[bool](../../dart-core/bool-class) clientNoContextTakeover = false,
2.  [bool](../../dart-core/bool-class) serverNoContextTakeover = false,
3.  [int](../../dart-core/int-class)? clientMaxWindowBits,
4.  [int](../../dart-core/int-class)? serverMaxWindowBits,
5.  [bool](../../dart-core/bool-class) enabled = true}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const CompressionOptions(
    {this.clientNoContextTakeover = false,
    this.serverNoContextTakeover = false,
    this.clientMaxWindowBits,
    this.serverMaxWindowBits,
    this.enabled = true});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/CompressionOptions/CompressionOptions.html>
:::
