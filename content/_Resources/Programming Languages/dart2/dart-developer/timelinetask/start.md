[dart:developer](../../dart-developer/dart-developer-library){._links-link}

start method
============

::: {.section .multi-line-signature}
void start(

1.  [String](../../dart-core/string-class) name,
2.  {[Map](../../dart-core/map-class)? arguments}

)
:::

Start a synchronous operation within this task named `name`. Optionally
takes a [Map](../../dart-core/map-class) of `arguments`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void start(String name, {Map? arguments}) {
  if (!_hasTimeline) return;
  // TODO: When NNBD is complete, delete the following line.
  ArgumentError.checkNotNull(name, 'name');
  if (!_isDartStreamEnabled()) {
    // Push a null onto the stack and return.
    _stack.add(null);
    return;
  }
  var block = new _AsyncBlock._(name, _taskId);
  _stack.add(block);
  // TODO(39115): Spurious error about collection literal ambiguity.
  // TODO(39117): Spurious error about typing of `...?arguments`.
  // TODO(39120): Spurious error even about `...arguments`.
  // When these TODOs are done, we can use spread and if elements.
  var map = <Object?, Object?>{};
  if (arguments != null) {
    for (var key in arguments.keys) {
      map[key] = arguments[key];
    }
  }
  if (_parent != null) map['parentId'] = _parent!._taskId.toRadixString(16);
  if (_filterKey != null) map[_kFilterKey] = _filterKey;
  block._start(map);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/TimelineTask/start.html>
:::
