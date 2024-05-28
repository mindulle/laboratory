[dart:core](../../dart-core/dart-core-library){._links-link}

Deprecated constructor
======================

::: {.section .multi-line-signature}
const Deprecated(

1.  [String](../string-class) message

)
:::

Create a deprecation annotation which specifies the migration path and
expiration of the annotated feature.

The [message](message) argument should be readable by programmers, and
should state an alternative feature (if available) as well as when an
annotated feature is expected to be removed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Deprecated(this.message);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Deprecated/Deprecated.html>
:::
