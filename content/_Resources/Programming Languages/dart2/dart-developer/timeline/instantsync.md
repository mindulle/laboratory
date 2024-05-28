[dart:developer](../../dart-developer/dart-developer-library){._links-link}

instantSync method
==================

::: {.section .multi-line-signature}
void instantSync(

1.  [String](../../dart-core/string-class) name,
2.  {[Map](../../dart-core/map-class)? arguments}

)
:::

Emit an instant event.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void instantSync(String name, {Map? arguments}) {
  if (!_hasTimeline) return;
  // TODO: When NNBD is complete, delete the following line.
  ArgumentError.checkNotNull(name, 'name');
  if (!_isDartStreamEnabled()) {
    // Stream is disabled.
    return;
  }
  Map? instantArguments;
  if (arguments != null) {
    instantArguments = new Map.from(arguments);
  }
  _reportInstantEvent('Dart', name, _argumentsAsJson(instantArguments));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Timeline/instantSync.html>
:::
