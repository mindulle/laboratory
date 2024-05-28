[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.empty constructor
=============================

::: {.section .multi-line-signature}
const Stream\<T\>.empty()
:::

Creates an empty broadcast stream.

This is a stream which does nothing except sending a done event when
it\'s listened to.

Example:

``` {.language-dart data-language="dart"}
const stream = Stream.empty();
stream.listen(
  (value) {
    throw "Unreachable";
  },
  onDone: () {
    print('Done');
  },
);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const factory Stream.empty() = _EmptyStream<T>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.empty.html>
:::
