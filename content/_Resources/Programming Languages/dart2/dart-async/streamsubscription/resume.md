[dart:async](../../dart-async/dart-async-library){._links-link}

resume method
=============

::: {.section .multi-line-signature}
void resume()
:::

Resumes after a pause.

This undoes one previous call to [pause](pause). When all previously
calls to [pause](pause) have been matched by a calls to
[resume](resume), possibly through a `resumeSignal` passed to
[pause](pause), the stream subscription may emit events again.

It is safe to [resume](resume) even when the subscription is not paused,
and the resume will have no effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void resume();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSubscription/resume.html>
:::
