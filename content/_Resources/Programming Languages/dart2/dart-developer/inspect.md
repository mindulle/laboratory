[dart:developer](../dart-developer/dart-developer-library){._links-link}

inspect function
================

::: {.section .multi-line-signature}
[Object](../dart-core/object-class)? inspect(

1.  [Object](../dart-core/object-class)? object

)
:::

Send a reference to `object` to any attached debuggers.

Debuggers may open an inspector on the object. Returns the argument.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Object? inspect(Object? object);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/inspect.html>
:::
