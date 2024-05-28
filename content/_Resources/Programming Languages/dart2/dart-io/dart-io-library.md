dart:io library
===============

File, socket, HTTP, and other I/O support for non-web applications.

**Important:** Browser-based apps can\'t use this library. Only the
following can import and use the dart:io library:

-   Servers
-   Command-line scripts
-   Flutter mobile apps
-   Flutter desktop apps

This library allows you to work with files, directories, sockets,
processes, HTTP servers and clients, and more. Many operations related
to input and output are asynchronous and are handled using
[Future](../dart-async/future-class)s or
[Stream](../dart-async/stream-class)s, both of which are defined in the
[dart:async library](../dart-async/dart-async-library).

To use the dart:io library in your code:

``` {.language-dart data-language="dart"}
import 'dart:io';
```

For an introduction to I/O in Dart, see the [dart:io library
tour](https://dart.dev/guides/libraries/library-tour#dartio).

File, Directory, and Link
-------------------------

An instance of [File](file-class), [Directory](directory-class), or
[Link](link-class) represents a file, directory, or link, respectively,
in the native file system.

You can manipulate the file system through objects of these types. For
example, you can rename a file or directory:

``` {.language-dart data-language="dart"}
File myFile = File('myFile.txt');
myFile.rename('yourFile.txt').then((_) => print('file renamed'));
```

Many methods provided by the [File](file-class),
[Directory](directory-class), and [Link](link-class) classes run
asynchronously and return a [Future](../dart-async/future-class).

FileSystemEntity
----------------

[File](file-class), [Directory](directory-class), and [Link](link-class)
all extend [FileSystemEntity](filesystementity-class). In addition to
being the superclass for these classes, FileSystemEntity has a number of
static methods for working with paths.

To get information about a path, you can use the
[FileSystemEntity](filesystementity-class) static methods such as
[FileSystemEntity.isDirectory](filesystementity/isdirectory),
[FileSystemEntity.isFile](filesystementity/isfile), and
[FileSystemEntity.exists](filesystementity/exists). Because file system
access involves I/O, these methods are asynchronous and return a
[Future](../dart-async/future-class).

``` {.language-dart data-language="dart"}
FileSystemEntity.isDirectory(myPath).then((isDir) {
  if (isDir) {
    print('$myPath is a directory');
  } else {
    print('$myPath is not a directory');
  }
});
```

HttpServer and HttpClient
-------------------------

The classes [HttpClient](httpclient-class) and
[HttpServer](httpserver-class) provide low-level HTTP functionality.

Instead of using these classes directly, consider using more
developer-friendly and composable APIs found in packages.

For HTTP clients, look at
[`package:http`](https://pub.dev/packages/http).

For HTTP servers, look at [Write HTTP
servers](https://dart.dev/tutorials/server/httpserver) on
[dart.dev](https://dart.dev/).

Process
-------

The [Process](process-class) class provides a way to run a process on
the native machine. For example, the following code spawns a process
that recursively lists the files under `web`.

``` {.language-dart data-language="dart"}
Process.start('ls', ['-R', 'web']).then((process) {
  stdout.addStream(process.stdout);
  stderr.addStream(process.stderr);
  process.exitCode.then(print);
});
```

Using [Process.start](process/start) returns a
[Future](../dart-async/future-class), which completes with a
[Process](process-class) object when the process has started. This
[Process](process-class) object allows you to interact with the process
while it is running. Using [Process.run](process/run) returns a
[Future](../dart-async/future-class), which completes with a
[ProcessResult](processresult-class) object when the spawned process has
terminated. This [ProcessResult](processresult-class) object collects
the output and exit code from the process.

When using [Process.start](process/start), you need to read all data
coming on the [Process.stdout](process/stdout) and
[Process.stderr](process/stderr) streams, otherwise the system resources
will not be freed.

WebSocket
---------

The [WebSocket](websocket-class) class provides support for the web
socket protocol. This allows full-duplex communications between client
and server applications.

A web socket server uses a normal HTTP server for accepting web socket
connections. The initial handshake is a HTTP request which is then
upgraded to a web socket connection. The server upgrades the request
using [WebSocketTransformer](websockettransformer-class) and listens for
the data on the returned web socket. For example, here\'s a mini server
that listens for \'ws\' data on a WebSocket:

``` {.language-dart data-language="dart"}
runZoned(() async {
  var server = await HttpServer.bind('127.0.0.1', 4040);
  server.listen((HttpRequest req) async {
    if (req.uri.path == '/ws') {
      var socket = await WebSocketTransformer.upgrade(req);
      socket.listen(handleMsg);
    }
  });
}, onError: (e) => print("An error occurred."));
```

The client connects to the [WebSocket](websocket-class) using the
[WebSocket.connect](websocket/connect) method and a URI that uses the
Web Socket protocol. The client can write to the
[WebSocket](websocket-class) with the [WebSocket.add](websocket/add)
method. For example,

``` {.language-dart data-language="dart"}
var socket = await WebSocket.connect('ws://127.0.0.1:4040/ws');
socket.add('Hello, World!');
```

Check out the
[websocket\_sample](https://github.com/dart-lang/dart-samples/tree/master/html5/web/websockets/basics)
app, which uses [WebSocket](websocket-class)s to communicate with a
server.

Socket and ServerSocket
-----------------------

Clients and servers use [Socket](socket-class)s to communicate using the
TCP protocol. Use [ServerSocket](serversocket-class) on the server side
and [Socket](socket-class) on the client. The server creates a listening
socket using the `bind()` method and then listens for incoming
connections on the socket. For example:

``` {.language-dart data-language="dart"}
ServerSocket.bind('127.0.0.1', 4041)
  .then((serverSocket) {
    serverSocket.listen((socket) {
      socket.transform(utf8.decoder).listen(print);
    });
  });
```

A client connects a [Socket](socket-class) using the `connect()` method,
which returns a [Future](../dart-async/future-class). Using `write()`,
`writeln()`, or `writeAll()` are the easiest ways to send data over the
socket. For example:

``` {.language-dart data-language="dart"}
Socket.connect('127.0.0.1', 4041).then((socket) {
  socket.write('Hello, World!');
});
```

Besides [Socket](socket-class) and [ServerSocket](serversocket-class),
the [RawSocket](rawsocket-class) and
[RawServerSocket](rawserversocket-class) classes are available for
lower-level access to async socket IO.

Standard output, error, and input streams
-----------------------------------------

This library provides the standard output, error, and input streams,
named [stdout](stdout), [stderr](stderr), and [stdin](stdin),
respectively.

The [stdout](stdout) and [stderr](stderr) streams are both
[IOSink](iosink-class)s and have the same set of methods and properties.

To write a string to [stdout](stdout):

``` {.language-dart data-language="dart"}
stdout.writeln('Hello, World!');
```

To write a list of objects to [stderr](stderr):

``` {.language-dart data-language="dart"}
stderr.writeAll([ 'That ', 'is ', 'an ', 'error.', '\n']);
```

The standard input stream is a true
[Stream](../dart-async/stream-class), so it inherits properties and
methods from the [Stream](../dart-async/stream-class) class.

To read text synchronously from the command line (the program blocks
waiting for user to type information):

``` {.language-dart data-language="dart"}
String? inputText = stdin.readLineSync();
```

Classes
-------

[BytesBuilder](../dart-typed_data/bytesbuilder-class)
:   Builds a list of bytes, allowing bytes and lists of bytes to be
    added at the end.

[CompressionOptions](compressionoptions-class)
:   Options controlling compression in a [WebSocket](websocket-class).

[ConnectionTask](connectiontask-class)\<S\>
:   A cancelable connection attempt.

[ContentType](contenttype-class)
:   A MIME/IANA media type used as the value of the
    [HttpHeaders.contentTypeHeader](httpheaders/contenttypeheader-constant)
    header.

[Cookie](cookie-class)
:   Representation of a cookie. For cookies received by the server as
    Cookie header values only [name](cookie/name) and
    [value](cookie/value) properties will be set. When building a cookie
    for the \'set-cookie\' header in the server and when receiving
    cookies in the client as \'set-cookie\' headers all fields can be
    used.

[Datagram](datagram-class)
:   A data packet received by a
    [RawDatagramSocket](rawdatagramsocket-class).

[Directory](directory-class)
:   A reference to a directory (or *folder*) on the file system.

[File](file-class)
:   A reference to a file on the file system.

[FileLock](filelock-class)
:   Type of lock when requesting a lock on a file.

[FileMode](filemode-class)
:   The modes in which a [File](file-class) can be opened.

[FileStat](filestat-class)
:   The result of calling the POSIX `stat()` function on a file system
    object.

[FileSystemCreateEvent](filesystemcreateevent-class)
:   File system event for newly created file system objects.

[FileSystemDeleteEvent](filesystemdeleteevent-class)
:   File system event for deletion of file system objects.

[FileSystemEntity](filesystementity-class)
:   The common superclass of [File](file-class),
    [Directory](directory-class), and [Link](link-class).

[FileSystemEntityType](filesystementitytype-class)
:   The type of an entity on the file system, such as a file, directory,
    or link.

[FileSystemEvent](filesystemevent-class)
:   Base event class emitted by
    [FileSystemEntity.watch](filesystementity/watch).

[FileSystemModifyEvent](filesystemmodifyevent-class)
:   File system event for modifications of file system objects.

[FileSystemMoveEvent](filesystemmoveevent-class)
:   File system event for moving of file system objects.

[GZipCodec](gzipcodec-class)
:   The [GZipCodec](gzipcodec-class) encodes raw bytes to GZip
    compressed bytes and decodes GZip compressed bytes to raw bytes.

[HeaderValue](headervalue-class)
:   Representation of a header value in the form:

[HttpClient](httpclient-class)
:   An HTTP client for communicating with an HTTP server.

[HttpClientBasicCredentials](httpclientbasiccredentials-class)
:   Represents credentials for basic authentication.

[HttpClientCredentials](httpclientcredentials-class)\
[HttpClientDigestCredentials](httpclientdigestcredentials-class)
:   Represents credentials for digest authentication. Digest
    authentication is only supported for servers using the MD5 algorithm
    and quality of protection (qop) of either \"none\" or \"auth\".

[HttpClientRequest](httpclientrequest-class)
:   HTTP request for a client connection.

[HttpClientResponse](httpclientresponse-class)
:   HTTP response for a client connection.

[HttpConnectionInfo](httpconnectioninfo-class)
:   Information about an [HttpRequest](httprequest-class),
    [HttpResponse](httpresponse-class),
    [HttpClientRequest](httpclientrequest-class), or
    [HttpClientResponse](httpclientresponse-class) connection.

[HttpConnectionsInfo](httpconnectionsinfo-class)
:   Summary statistics about an [HttpServer](httpserver-class)s current
    socket connections.

[HttpDate](httpdate-class)
:   Utility functions for working with dates with HTTP specific date
    formats.

[HttpHeaders](httpheaders-class)
:   Headers for HTTP requests and responses.

[HttpOverrides](httpoverrides-class)
:   This class facilitates overriding [HttpClient](httpclient-class)
    with a mock implementation. It should be extended by another class
    in client code with overrides that construct a mock implementation.
    The implementation in this base class defaults to the actual
    [HttpClient](httpclient-class) implementation. For example:

[HttpRequest](httprequest-class)
:   A server-side object that contains the content of and information
    about an HTTP request.

[HttpResponse](httpresponse-class)
:   An HTTP response, which returns the headers and data from the server
    to the client in response to an HTTP request.

[HttpServer](httpserver-class)
:   A server that delivers content, such as web pages, using the HTTP
    protocol.

[HttpSession](httpsession-class)
:   The [HttpRequest.session](httprequest/session) of an
    [HttpRequest](httprequest-class).

[HttpStatus](../dart-html/httpstatus-class)
:   HTTP status codes. Exported in dart:io and dart:html.

[InternetAddress](internetaddress-class)
:   An internet address or a Unix domain address.

[InternetAddressType](internetaddresstype-class)
:   The type, or address family, of an
    [InternetAddress](internetaddress-class).

[IOOverrides](iooverrides-class)
:   Facilities for overriding various APIs of `dart:io` with mock
    implementations.

[IOSink](iosink-class)
:   A combined byte and text output.

[Link](link-class)
:   References to filesystem links.

[NetworkInterface](networkinterface-class)
:   A [NetworkInterface](networkinterface-class) represents an active
    network interface on the current system. It contains a list of
    [InternetAddress](internetaddress-class)es that are bound to the
    interface.

[Platform](platform-class)
:   Information about the environment in which the current program is
    running.

[Process](process-class)
:   The means to execute a program.

[ProcessInfo](processinfo-class)
:   Methods for retrieving information about the current process.

[ProcessResult](processresult-class)
:   The result of running a non-interactive process started with
    [Process.run](process/run) or [Process.runSync](process/runsync).

[ProcessSignal](processsignal-class)
:   On Posix systems, [ProcessSignal](processsignal-class) is used to
    send a specific signal to a child process, see `Process.kill`.

[ProcessStartMode](processstartmode-class)
:   Modes for running a new process.

[RandomAccessFile](randomaccessfile-class)
:   Random access to the data in a file.

[RawDatagramSocket](rawdatagramsocket-class)
:   An unbuffered interface to a UDP socket.

[RawSecureServerSocket](rawsecureserversocket-class)
:   A server socket providing a stream of low-level
    [RawSecureSocket](rawsecuresocket-class)s.

[RawSecureSocket](rawsecuresocket-class)
:   `RawSecureSocket` provides a secure (SSL or TLS) network connection.

[RawServerSocket](rawserversocket-class)
:   A listening socket.

[RawSocket](rawsocket-class)
:   A TCP connection.

[RawSocketEvent](rawsocketevent-class)
:   Events for the [RawSocket](rawsocket-class).

[RawSocketOption](rawsocketoption-class)
:   The [RawSocketOption](rawsocketoption-class) is used as a parameter
    to [Socket.setRawOption](socket/setrawoption) and
    [RawSocket.setRawOption](rawsocket/setrawoption) to customize the
    behaviour of the underlying socket.

[RawSynchronousSocket](rawsynchronoussocket-class)
:   A low-level class for communicating synchronously over a TCP socket.

[RawZLibFilter](rawzlibfilter-class)
:   The [RawZLibFilter](rawzlibfilter-class) class provides a low-level
    interface to zlib.

[RedirectInfo](redirectinfo-class)
:   Redirect information.

[ResourceHandle](resourcehandle-class)
:   A wrappper around OS resource handle so it can be passed via Socket
    as part of [SocketMessage](socketmessage-class).

[SecureServerSocket](secureserversocket-class)
:   A server socket, providing a stream of high-level
    [Socket](socket-class)s.

[SecureSocket](securesocket-class)
:   A TCP socket using TLS and SSL.

[SecurityContext](securitycontext-class)
:   The object containing the certificates to trust when making a secure
    client connection, and the certificate chain and private key to
    serve from a secure server.

[ServerSocket](serversocket-class)
:   A listening socket.

[Socket](socket-class)
:   A TCP connection between two sockets.

[SocketControlMessage](socketcontrolmessage-class)
:   Control message part of the [SocketMessage](socketmessage-class)
    received by a call to
    [RawSocket.readMessage](rawsocket/readmessage).

[SocketDirection](socketdirection-class)
:   The [SocketDirection](socketdirection-class) is used as a parameter
    to [Socket.close](socket/close) and
    [RawSocket.close](rawsocket/close) to close a socket in the
    specified direction(s).

[SocketMessage](socketmessage-class)
:   A socket message received by a
    [RawDatagramSocket](rawdatagramsocket-class).

[SocketOption](socketoption-class)
:   An option for a socket which is configured using
    [Socket.setOption](socket/setoption).

[Stdin](stdin-class)
:   The standard input stream of the process.

[StdioType](stdiotype-class)
:   The type of object a standard IO stream can be attached to.

[Stdout](stdout-class)
:   An [IOSink](iosink-class) connected to either the standard out or
    error of the process.

[SystemEncoding](systemencoding-class)
:   The system encoding is the current code page on Windows and UTF-8 on
    Linux and Mac.

[WebSocket](websocket-class)
:   A two-way HTTP communication object for client or server
    applications.

[WebSocketStatus](websocketstatus-class)
:   WebSocket status codes used when closing a WebSocket connection.

[WebSocketTransformer](websockettransformer-class)
:   The [WebSocketTransformer](websockettransformer-class) provides the
    ability to upgrade a [HttpRequest](httprequest-class) to a
    [WebSocket](websocket-class) connection. It supports both upgrading
    a single [HttpRequest](httprequest-class) and upgrading a stream of
    [HttpRequest](httprequest-class)s.

[X509Certificate](x509certificate-class)
:   X509Certificate represents an SSL certificate, with accessors to get
    the fields of the certificate.

[ZLibCodec](zlibcodec-class)
:   The [ZLibCodec](zlibcodec-class) encodes raw bytes to ZLib
    compressed bytes and decodes ZLib compressed bytes to raw bytes.

[ZLibDecoder](zlibdecoder-class)
:   The [ZLibDecoder](zlibdecoder-class) is used by
    [ZLibCodec](zlibcodec-class) and [GZipCodec](gzipcodec-class) to
    decompress data.

[ZLibEncoder](zlibencoder-class)
:   The [ZLibEncoder](zlibencoder-class) encoder is used by
    [ZLibCodec](zlibcodec-class) and [GZipCodec](gzipcodec-class) to
    compress data.

[ZLibOption](zliboption-class)
:   Exposes ZLib options for input parameters.

Constants
---------

[gzip](gzip-constant) → const [GZipCodec](gzipcodec-class)
:   An instance of the default implementation of the
    [GZipCodec](gzipcodec-class).
    <div>

    `const GZipCodec._default()`

    </div>

[systemEncoding](systemencoding-constant) → const [SystemEncoding](systemencoding-class)
:   The current system encoding.
    <div>

    `const SystemEncoding()`

    </div>

[zlib](zlib-constant) → const [ZLibCodec](zlibcodec-class)
:   An instance of the default implementation of the
    [ZLibCodec](zlibcodec-class).
    <div>

    `const ZLibCodec._default()`

    </div>

Properties
----------

[exitCode](exitcode) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

Get the global exit code for the Dart VM.

[pid](pid) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Returns the PID of the current process.

[stderr](stderr) → [Stdout](stdout-class)

::: {.features}
read-only
:::

The standard output stream of errors written by this program.

[stdin](stdin) → [Stdin](stdin-class)

::: {.features}
read-only
:::

The standard input stream of data read by this program.

[stdout](stdout) → [Stdout](stdout-class)

::: {.features}
read-only
:::

The standard output stream of data written by this program.

Functions
---------

[exit](exit)([int](../dart-core/int-class) code) → Never
:   Exit the Dart VM process immediately with the given exit code.

[sleep](sleep)([Duration](../dart-core/duration-class) duration) → void
:   Sleep for the duration specified in `duration`.

[stdioType](stdiotype)(dynamic object) → [StdioType](stdiotype-class)
:   Whether a stream is attached to a file, pipe, terminal, or something
    else.

Enums
-----

[HttpClientResponseCompressionState](httpclientresponsecompressionstate)
:   Enum that specifies the compression state of the byte stream of an
    [HttpClientResponse](httpclientresponse-class).

Typedefs
--------

[BadCertificateCallback](badcertificatecallback) =
[bool](../dart-core/bool-class)
Function([X509Certificate](x509certificate-class) cr,
[String](../dart-core/string-class) host, [int](../dart-core/int-class)
port)

Exceptions / Errors {#exceptions}
-------------------

[CertificateException](certificateexception-class)

An exception that happens in the handshake phase of establishing a
secure network connection, when looking up or verifying a certificate.

[FileSystemException](filesystemexception-class)

Exception thrown when a file operation fails.

[HandshakeException](handshakeexception-class)

An exception that happens in the handshake phase of establishing a
secure network connection.

[HttpException](httpexception-class)

[IOException](ioexception-class)

Base class for all IO related exceptions.

[OSError](oserror-class)

An [Exception](../dart-core/exception-class) holding information about
an error from the operating system.

[ProcessException](processexception-class)

[RedirectException](redirectexception-class)

[SignalException](signalexception-class)

[SocketException](socketexception-class)

Exception thrown when a socket operation fails.

[StdinException](stdinexception-class)

Exception thrown by some operations of [Stdin](stdin-class)

[StdoutException](stdoutexception-class)

Exception thrown by some operations of [Stdout](stdout-class)

[TlsException](tlsexception-class)

A secure networking exception caused by a failure in the TLS/SSL
protocol.

[WebSocketException](websocketexception-class)

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/dart-io-library.html>
:::
