[dart:core](../../dart-core/dart-core-library){._links-link}

toLowerCase method
==================

::: {.section .multi-line-signature}
[String](../string-class) toLowerCase()
:::

Converts all characters in this string to lower case.

If the string is already in all lower case, this method returns `this`.

``` {.language-dart data-language="dart"}
'ALPHABET'.toLowerCase(); // 'alphabet'
'abc'.toLowerCase(); // 'abc'
```

This function uses the language independent Unicode mapping and thus
only works in some languages.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// TODO(floitsch): document better. (See EcmaScript for description).
String toLowerCase();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/toLowerCase.html>
:::
