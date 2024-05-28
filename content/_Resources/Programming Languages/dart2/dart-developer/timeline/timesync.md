[dart:developer](../../dart-developer/dart-developer-library){._links-link}

timeSync\<T\> method
====================

::: {.section .multi-line-signature}
T timeSync\<T\>(

1.  [String](../../dart-core/string-class) name,
2.  [TimelineSyncFunction](../timelinesyncfunction)\<T\> function,
3.  {[Map](../../dart-core/map-class)? arguments,
4.  [Flow](../flow-class)? flow}

)
:::

A utility method to time a synchronous `function`. Internally calls
`function` bracketed by calls to [startSync](startsync) and
[finishSync](finishsync).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static T timeSync<T>(String name, TimelineSyncFunction<T> function,
    {Map? arguments, Flow? flow}) {
  startSync(name, arguments: arguments, flow: flow);
  try {
    return function();
  } finally {
    finishSync();
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Timeline/timeSync.html>
:::
