[dart:core](../dart-core/dart-core-library){._links-link}

print function
==============

::: {.section .multi-line-signature}
void print(

1.  [Object](object-class)? object

)
:::

Prints a string representation of the object to the console.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void print(Object? object) {
  String line = "$object";
  var toZone = printToZone;
  if (toZone == null) {
    printToConsole(line);
  } else {
    toZone(line);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/print.html>
:::
