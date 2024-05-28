[dart:developer](../../dart-developer/dart-developer-library){._links-link}

isError method
==============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isError()
:::

Determines if this response represents an error.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool isError() => (errorCode != null) && (errorDetail != null);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/ServiceExtensionResponse/isError.html>
:::
