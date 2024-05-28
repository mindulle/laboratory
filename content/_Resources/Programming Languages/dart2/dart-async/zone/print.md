[dart:async](../../dart-async/dart-async-library){._links-link}

print method
============

::: {.section .multi-line-signature}
void print(

1.  [String](../../dart-core/string-class) line

)
:::

Prints the given `line`.

The global `print` function delegates to the current zone\'s
[print](print) function which makes it possible to intercept printing.

Example:

``` {.language-dart data-language="dart"}
import 'dart:async';

main() {
  runZoned(() {
    // Ends up printing: "Intercepted: in zone".
    print("in zone");
  }, zoneSpecification: new ZoneSpecification(
      print: (Zone self, ZoneDelegate parent, Zone zone, String line) {
    parent.print(zone, "Intercepted: $line");
  }));
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void print(String line);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/print.html>
:::
