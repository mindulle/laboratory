[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

suspendFor method
=================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'suspend\')

</div>

[Future](../../dart-async/future-class) suspendFor(

1.  [num](../../dart-core/num-class) suspendTime

)

::: {.features}
\@JSName(\'suspend\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('suspend')
Future suspendFor(num suspendTime) =>
    promiseToFuture(JS("", "#.suspend(#)", this, suspendTime));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/OfflineAudioContext/suspendFor.html>
:::
