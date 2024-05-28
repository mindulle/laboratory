[dart:io](../../dart-io/dart-io-library){._links-link}

readLineSync method
===================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class)? readLineSync(

1.  {[Encoding](../../dart-convert/encoding-class) encoding =
    systemEncoding,
2.  [bool](../../dart-core/bool-class) retainNewlines = false}

)
:::

Reads a line from stdin.

Blocks until a full line is available.

Lines my be terminated by either `<CR><LF>` or `<LF>`. On Windows, in
cases where the [stdioType](../stdiotype) of stdin is
[StdioType.terminal](../stdiotype/terminal-constant), the terminator may
also be a single `<CR>`.

Input bytes are converted to a string by `encoding`. If `encoding` is
omitted, it defaults to [systemEncoding](../systemencoding-constant).

If `retainNewlines` is `false`, the returned string will not include the
final line terminator. If `true`, the returned string will include the
line terminator. Default is `false`.

If end-of-file is reached after any bytes have been read from stdin,
that data is returned without a line terminator. Returns `null` if no
bytes preceded the end of input.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? readLineSync(
    {Encoding encoding = systemEncoding, bool retainNewlines = false}) {
  const CR = 13;
  const LF = 10;
  final List<int> line = <int>[];
  // On Windows, if lineMode is disabled, only CR is received.
  bool crIsNewline = Platform.isWindows &&
      (stdioType(stdin) == StdioType.terminal) &&
      !lineMode;
  if (retainNewlines) {
    int byte;
    do {
      byte = readByteSync();
      if (byte < 0) {
        break;
      }
      line.add(byte);
    } while (byte != LF && !(byte == CR && crIsNewline));
    if (line.isEmpty) {
      return null;
    }
  } else if (crIsNewline) {
    // CR and LF are both line terminators, neither is retained.
    while (true) {
      int byte = readByteSync();
      if (byte < 0) {
        if (line.isEmpty) return null;
        break;
      }
      if (byte == LF || byte == CR) break;
      line.add(byte);
    }
  } else {
    // Case having to handle CR LF as a single unretained line terminator.
    outer:
    while (true) {
      int byte = readByteSync();
      if (byte == LF) break;
      if (byte == CR) {
        do {
          byte = readByteSync();
          if (byte == LF) break outer;

          line.add(CR);
        } while (byte == CR);
        // Fall through and handle non-CR character.
      }
      if (byte < 0) {
        if (line.isEmpty) return null;
        break;
      }
      line.add(byte);
    }
  }
  return encoding.decode(line);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdin/readLineSync.html>
:::
