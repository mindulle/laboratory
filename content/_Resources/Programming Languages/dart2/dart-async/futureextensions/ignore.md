[dart:async](../../dart-async/dart-async-library){._links-link}

ignore method
=============

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.14\")

</div>

void ignore()

::: {.features}
\@Since(\"2.14\")
:::
:::

Completely ignores this future and its result.

Not all futures are important, not even if they contain errors, for
example if a request was made, but the response is no longer needed.
Simply ignoring a future can result in uncaught asynchronous errors.
This method instead handles (and ignores) any values or errors coming
from this future, making it safe to otherwise ignore the future.

Use `ignore` to signal that the result of the future is no longer
important to the program, not even if it\'s an error. If you merely want
to silence the [\"unawaited futures\"
lint](https://dart-lang.github.io/linter/lints/unawaited_futures.html),
use the [unawaited](../unawaited) function instead. That will ensure
that an unexpected error is still reported.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.14")
void ignore() {
  var self = this;
  if (self is _Future<T>) {
    self._ignore();
  } else {
    self.then<void>(_ignore, onError: _ignore);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/FutureExtensions/ignore.html>
:::
