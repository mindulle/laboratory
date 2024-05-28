[dart:developer](../../dart-developer/dart-developer-library){._links-link}

startSync method
================

::: {.section .multi-line-signature}
void startSync(

1.  [String](../../dart-core/string-class) name,
2.  {[Map](../../dart-core/map-class)? arguments,
3.  [Flow](../flow-class)? flow}

)
:::

Start a synchronous operation labeled `name`. Optionally takes a
[Map](../../dart-core/map-class) of `arguments`. This slice may also
optionally be associated with a [Flow](../flow-class) event. This
operation must be finished before returning to the event queue.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void startSync(String name, {Map? arguments, Flow? flow}) {
  if (!_hasTimeline) return;
  // TODO: When NNBD is complete, delete the following line.
  ArgumentError.checkNotNull(name, 'name');
  if (!_isDartStreamEnabled()) {
    // Push a null onto the stack and return.
    _stack.add(null);
    return;
  }
  var block = new _SyncBlock._(name, arguments: arguments, flow: flow);
  _stack.add(block);
  block._startSync();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Timeline/startSync.html>
:::
