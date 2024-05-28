[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

RemoteError constructor
=======================

::: {.section .multi-line-signature}
RemoteError(

1.  [String](../../dart-core/string-class) description,
2.  [String](../../dart-core/string-class) stackDescription

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RemoteError(String description, String stackDescription)
    : _description = description,
      stackTrace = StackTrace.fromString(stackDescription);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/RemoteError/RemoteError.html>
:::
