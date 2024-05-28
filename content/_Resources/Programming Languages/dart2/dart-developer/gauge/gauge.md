[dart:developer](../../dart-developer/dart-developer-library){._links-link}

Gauge constructor
=================

::: {.section .multi-line-signature}
Gauge(

1.  [String](../../dart-core/string-class) name,
2.  [String](../../dart-core/string-class) description,
3.  [double](../../dart-core/double-class) min,
4.  [double](../../dart-core/double-class) max

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Gauge(String name, String description, this.min, this.max)
    : _value = min,
      super(name, description) {
  // TODO: When NNBD is complete, delete the following two lines.
  ArgumentError.checkNotNull(min, 'min');
  ArgumentError.checkNotNull(max, 'max');
  if (!(min < max)) throw new ArgumentError('min must be less than max');
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Gauge/Gauge.html>
:::
