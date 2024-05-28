[dart:developer](../../dart-developer/dart-developer-library){._links-link}

deregister method
=================

::: {.section .multi-line-signature}
void deregister(

1.  [Metric](../metric-class) metric

)
:::

Deregister [Metric](../metric-class)s to make them not visible to
Observatory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void deregister(Metric metric) {
  // TODO: When NNBD is complete, delete the following line.
  ArgumentError.checkNotNull(metric, 'metric');
  _metrics.remove(metric.name);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Metrics/deregister.html>
:::
