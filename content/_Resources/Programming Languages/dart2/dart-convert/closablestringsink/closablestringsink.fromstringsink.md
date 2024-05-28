[dart:convert](../../dart-convert/dart-convert-library){._links-link}

ClosableStringSink.fromStringSink constructor
=============================================

::: {.section .multi-line-signature}
ClosableStringSink.fromStringSink(

1.  [StringSink](../../dart-core/stringsink-class) sink,
2.  void onClose( )

)
:::

Creates a new instance combining a
[StringSink](../../dart-core/stringsink-class) `sink` and a callback
`onClose` which is invoked when the returned instance is closed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ClosableStringSink.fromStringSink(StringSink sink, void onClose()) =
    _ClosableStringSink;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/ClosableStringSink/ClosableStringSink.fromStringSink.html>
:::
