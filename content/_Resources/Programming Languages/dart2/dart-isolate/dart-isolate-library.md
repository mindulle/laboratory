dart:isolate library
====================

Concurrent programming using *isolates*: independent workers that are
similar to threads but don\'t share memory, communicating only via
messages.

*NOTE*: The `dart:isolate` library is currently only supported by the
[Dart Native](https://dart.dev/overview#platform) platform.

To use this library in your code:

``` {.language-dart data-language="dart"}
import 'dart:isolate';
```

Classes
-------

[Capability](capability-class)
:   An unforgeable object that comes back as equal when passed through
    other isolates.

[Isolate](isolate-class)
:   An isolated Dart execution context.

[RawReceivePort](rawreceiveport-class)
:   A low-level asynchronous message receiver.

[ReceivePort](receiveport-class)
:   Together with [SendPort](sendport-class), the only means of
    communication between isolates.

[SendPort](sendport-class)
:   Sends messages to its [ReceivePort](receiveport-class)s.

[TransferableTypedData](transferabletypeddata-class)
:   An efficiently transferable sequence of byte values.

Exceptions / Errors {#exceptions}
-------------------

[IsolateSpawnException](isolatespawnexception-class)
:   Thrown when an isolate cannot be created.

[RemoteError](remoteerror-class)
:   Description of an error from another isolate.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/dart-isolate-library.html>
:::
