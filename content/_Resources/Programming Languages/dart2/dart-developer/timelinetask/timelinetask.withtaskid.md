[dart:developer](../../dart-developer/dart-developer-library){._links-link}

TimelineTask.withTaskId constructor
===================================

::: {.section .multi-line-signature}
TimelineTask.withTaskId(

1.  [int](../../dart-core/int-class) taskId,
2.  {[String](../../dart-core/string-class)? filterKey}

)
:::

Create a task with an explicit `taskId`. This is useful if you are
passing a task from one isolate to another.

Important note: only provide task IDs which have been obtained as a
result of invoking [TimelineTask.pass](pass). Specifying a custom ID can
lead to ID collisions, resulting in incorrect rendering of timeline
events.

If `filterKey` is provided, a property named `filterKey` will be
inserted into the arguments of each event associated with this task. The
`filterKey` will be set to the value of `filterKey`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
TimelineTask.withTaskId(int taskId, {String? filterKey})
    : _parent = null,
      _filterKey = filterKey,
      _taskId = taskId {
  // TODO: When NNBD is complete, delete the following line.
  ArgumentError.checkNotNull(taskId, 'taskId');
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/TimelineTask/TimelineTask.withTaskId.html>
:::
