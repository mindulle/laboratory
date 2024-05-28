[dart:convert](../../dart-convert/dart-convert-library){._links-link}

asStringSink method
===================

::: {.section .multi-line-signature}
[ClosableStringSink](../closablestringsink-class) asStringSink()
:::

Returns `this` as a [ClosableStringSink](../closablestringsink-class).

If used, this method must be the first and only call to `this`. It
invalidates `this`. All further operations must be performed on the
result.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ClosableStringSink asStringSink();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/StringConversionSink/asStringSink.html>
:::
