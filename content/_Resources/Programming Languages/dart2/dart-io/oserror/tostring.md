[dart:io](../../dart-io/dart-io-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) toString()

::: {.features}
override
:::
:::

Converts an OSError object to a string representation.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() {
  StringBuffer sb = new StringBuffer();
  sb.write("OS Error");
  if (message.isNotEmpty) {
    sb..write(": ")..write(message);
    if (errorCode != noErrorCode) {
      sb..write(", errno = ")..write(errorCode.toString());
    }
  } else if (errorCode != noErrorCode) {
    sb..write(": errno = ")..write(errorCode.toString());
  }
  return sb.toString();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/OSError/toString.html>
:::
