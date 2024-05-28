[dart:developer](../../dart-developer/dart-developer-library){._links-link}

TimelineTask constructor
========================

::: {.section .multi-line-signature}
TimelineTask(

1.  {[TimelineTask](../timelinetask-class)? parent,
2.  [String](../../dart-core/string-class)? filterKey}

)
:::

Create a task. The task ID will be set by the system.

If `parent` is provided, the parent\'s task ID is provided as argument
\'parentId\' when [start](start) is called. In DevTools, this argument
will result in this [TimelineTask](../timelinetask-class) being linked
to the `parent` [TimelineTask](../timelinetask-class).

If `filterKey` is provided, a property named `filterKey` will be
inserted into the arguments of each event associated with this task. The
`filterKey` will be set to the value of `filterKey`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
TimelineTask({TimelineTask? parent, String? filterKey})
    : _parent = parent,
      _filterKey = filterKey,
      _taskId = _getNextAsyncId() {}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/TimelineTask/TimelineTask.html>
:::
