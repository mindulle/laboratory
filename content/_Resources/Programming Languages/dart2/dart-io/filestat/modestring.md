[dart:io](../../dart-io/dart-io-library){._links-link}

modeString method
=================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) modeString()
:::

The mode value as a human-readable string.

The string is in the format \"rwxrwxrwx\", reflecting the user, group,
and world permissions to read, write, and execute the file system
object, with \"-\" replacing the letter for missing permissions. Extra
permission bits may be represented by prepending \"(suid)\", \"(guid)\",
and/or \"(sticky)\" to the mode string.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String modeString() {
  var permissions = mode & 0xFFF;
  var codes = const ['---', '--x', '-w-', '-wx', 'r--', 'r-x', 'rw-', 'rwx'];
  var result = [];
  if ((permissions & 0x800) != 0) result.add("(suid) ");
  if ((permissions & 0x400) != 0) result.add("(guid) ");
  if ((permissions & 0x200) != 0) result.add("(sticky) ");
  result
    ..add(codes[(permissions >> 6) & 0x7])
    ..add(codes[(permissions >> 3) & 0x7])
    ..add(codes[permissions & 0x7]);
  return result.join();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileStat/modeString.html>
:::
