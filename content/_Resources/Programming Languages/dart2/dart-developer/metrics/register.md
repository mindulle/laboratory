[dart:developer](../../dart-developer/dart-developer-library){._links-link}

register method
===============

::: {.section .multi-line-signature}
void register(

1.  [Metric](../metric-class) metric

)
:::

Register [Metric](../metric-class)s to make them visible to Observatory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void register(Metric metric) {
  // TODO: When NNBD is complete, delete the following line.
  ArgumentError.checkNotNull(metric, 'metric');
  if (_metrics[metric.name] != null) {
    throw new ArgumentError('Registered metrics have unique names');
  }
  _metrics[metric.name] = metric;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Metrics/register.html>
:::
