[dart:html](../../dart-html/dart-html-library){._links-link}

getStats method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RtcStatsReport](../rtcstatsreport-class)\>
getStats()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RtcStatsReport> getStats() => promiseToFuture<RtcStatsReport>(
    JS("creates:RtcStatsReport;", "#.getStats()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/getStats.html>
:::
