[dart:developer](../../dart-developer/dart-developer-library){._links-link}

instant method
==============

::: {.section .multi-line-signature}
void instant(

1.  [String](../../dart-core/string-class) name,
2.  {[Map](../../dart-core/map-class)? arguments}

)
:::

Emit an instant event for this task. Optionally takes a
[Map](../../dart-core/map-class) of `arguments`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void instant(String name, {Map? arguments}) {
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
  if (_filterKey != null) {
    instantArguments ??= {};
    instantArguments[_kFilterKey] = _filterKey;
  }
  _reportTaskEvent(
      _taskId, 'n', 'Dart', name, _argumentsAsJson(instantArguments));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/TimelineTask/instant.html>
:::
