[dart:io](../dart-io/dart-io-library){._links-link}

stdioType function
==================

::: {.section .multi-line-signature}
[StdioType](stdiotype-class) stdioType(

1.  dynamic object

)
:::

Whether a stream is attached to a file, pipe, terminal, or something
else.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
StdioType stdioType(object) {
  if (object is _StdStream) {
    object = object._stream;
  } else if (object == stdout || object == stderr) {
    int stdiofd = object == stdout ? _stdoutFD : _stderrFD;
    final type = _StdIOUtils._getStdioHandleType(stdiofd);
    if (type is OSError) {
      throw FileSystemException(
          "Failed to get type of stdio handle (fd $stdiofd)", "", type);
    }
    switch (type) {
      case _stdioHandleTypeTerminal:
        return StdioType.terminal;
      case _stdioHandleTypePipe:
        return StdioType.pipe;
      case _stdioHandleTypeFile:
        return StdioType.file;
    }
  }
  if (object is _FileStream) {
    return StdioType.file;
  }
  if (object is Socket) {
    int? socketType = _StdIOUtils._socketType(object);
    if (socketType == null) return StdioType.other;
    switch (socketType) {
      case _stdioHandleTypeTerminal:
        return StdioType.terminal;
      case _stdioHandleTypePipe:
        return StdioType.pipe;
      case _stdioHandleTypeFile:
        return StdioType.file;
    }
  }
  if (object is _IOSinkImpl) {
    try {
      if (object._target is _FileStreamConsumer) {
        return StdioType.file;
      }
    } catch (e) {
      // Only the interface implemented, _sink not available.
    }
  }
  return StdioType.other;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/stdioType.html>
:::
