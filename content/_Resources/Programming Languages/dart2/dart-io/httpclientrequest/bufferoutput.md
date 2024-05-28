[dart:io](../../dart-io/dart-io-library){._links-link}

bufferOutput property
=====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) bufferOutput

::: {.features}
read / write
:::
:::

Gets or sets if the [HttpClientRequest](../httpclientrequest-class)
should buffer output.

Default value is `true`.

**Note**: Disabling buffering of the output can result in very poor
performance, when writing many small chunks.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool bufferOutput = true;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientRequest/bufferOutput.html>
:::
