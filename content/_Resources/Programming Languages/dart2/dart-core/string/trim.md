[dart:core](../../dart-core/dart-core-library){._links-link}

trim method
===========

::: {.section .multi-line-signature}
[String](../string-class) trim()
:::

The string without any leading and trailing whitespace.

If the string contains leading or trailing whitespace, a new string with
no leading and no trailing whitespace is returned:

``` {.language-dart data-language="dart"}
final trimmed = '\tDart is fun\n'.trim();
print(trimmed); // 'Dart is fun'
```

Otherwise, the original string itself is returned:

``` {.language-dart data-language="dart"}
const string1 = 'Dart';
final string2 = string1.trim(); // 'Dart'
print(identical(string1, string2)); // true
```

Whitespace is defined by the Unicode White\_Space property (as defined
in version 6.2 or later) and the BOM character, 0xFEFF.

Here is the list of trimmed characters according to Unicode version 6.3:

``` {.language-plaintext data-language="dart"}
0009..000D    ; White_Space # Cc   <control-0009>..<control-000D>
    0020          ; White_Space # Zs   SPACE
    0085          ; White_Space # Cc   <control-0085>
    00A0          ; White_Space # Zs   NO-BREAK SPACE
    1680          ; White_Space # Zs   OGHAM SPACE MARK
    2000..200A    ; White_Space # Zs   EN QUAD..HAIR SPACE
    2028          ; White_Space # Zl   LINE SEPARATOR
    2029          ; White_Space # Zp   PARAGRAPH SEPARATOR
    202F          ; White_Space # Zs   NARROW NO-BREAK SPACE
    205F          ; White_Space # Zs   MEDIUM MATHEMATICAL SPACE
    3000          ; White_Space # Zs   IDEOGRAPHIC SPACE

    FEFF          ; BOM                ZERO WIDTH NO_BREAK SPACE
```

Some later versions of Unicode do not include U+0085 as a whitespace
character. Whether it is trimmed depends on the Unicode version used by
the system.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String trim();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/trim.html>
:::
