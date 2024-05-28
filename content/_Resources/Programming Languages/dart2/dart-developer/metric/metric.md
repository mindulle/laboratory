[dart:developer](../../dart-developer/dart-developer-library){._links-link}

Metric constructor
==================

::: {.section .multi-line-signature}
Metric(

1.  [String](../../dart-core/string-class) name,
2.  [String](../../dart-core/string-class) description

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Metric(this.name, this.description) {
  if ((name == 'vm') || name.contains('/')) {
    throw new ArgumentError('Invalid Metric name.');
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Metric/Metric.html>
:::
