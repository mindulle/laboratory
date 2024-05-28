dart:convert library
====================

Encoders and decoders for converting between different data
representations, including JSON and UTF-8.

In addition to converters for common data representations, this library
provides support for implementing converters in a way which makes them
easy to chain and to use with streams.

To use this library in your code:

``` {.language-dart data-language="dart"}
import 'dart:convert';
```

Two commonly used converters are the top-level instances of
[JsonCodec](jsoncodec-class) and [Utf8Codec](utf8codec-class), named
[json](json-constant) and [utf8](utf8-constant), respectively.

JSON
----

JSON is a simple text format for representing structured objects and
collections.

A [JsonCodec](jsoncodec-class) encodes JSON objects to strings and
decodes strings to JSON objects. The [json](json-constant)
encoder/decoder transforms between strings and object structures, such
as lists and maps, using the JSON format.

The [json](json-constant) is the default implementation of
[JsonCodec](jsoncodec-class).

Examples

``` {.language-dart data-language="dart"}
var encoded = json.encode([1, 2, { "a": null }]);
var decoded = json.decode('["foo", { "bar": 499 }]');
```

For more information, see also [JsonEncoder](jsonencoder-class) and
[JsonDecoder](jsondecoder-class).

UTF-8
-----

A [Utf8Codec](utf8codec-class) encodes strings to UTF-8 code units
(bytes) and decodes UTF-8 code units to strings.

The [utf8](utf8-constant) is the default implementation of
[Utf8Codec](utf8codec-class).

Example:

``` {.language-dart data-language="dart"}
var encoded = utf8.encode('Îñţérñåţîöñåļîžåţîờñ');
var decoded = utf8.decode([
  195, 142, 195, 177, 197, 163, 195, 169, 114, 195, 177, 195, 165, 197,
  163, 195, 174, 195, 182, 195, 177, 195, 165, 196, 188, 195, 174, 197,
  190, 195, 165, 197, 163, 195, 174, 225, 187, 157, 195, 177]);
```

For more information, see also [Utf8Encoder](utf8encoder-class) and
[Utf8Decoder](utf8decoder-class).

ASCII
-----

An [AsciiCodec](asciicodec-class) encodes strings as ASCII codes stored
as bytes and decodes ASCII bytes to strings. Not all characters can be
represented as ASCII, so not all strings can be successfully converted.

The [ascii](ascii-constant) is the default implementation of
[AsciiCodec](asciicodec-class).

Example:

``` {.language-dart data-language="dart"}
var encoded = ascii.encode('This is ASCII!');
var decoded = ascii.decode([0x54, 0x68, 0x69, 0x73, 0x20, 0x69, 0x73,
                            0x20, 0x41, 0x53, 0x43, 0x49, 0x49, 0x21]);
```

For more information, see also [AsciiEncoder](asciiencoder-class) and
[AsciiDecoder](asciidecoder-class).

Latin-1
-------

A [Latin1Codec](latin1codec-class) encodes strings to ISO Latin-1 (aka
ISO-8859-1) bytes and decodes Latin-1 bytes to strings. Not all
characters can be represented as Latin-1, so not all strings can be
successfully converted.

The [latin1](latin1-constant) is the default implementation of
[Latin1Codec](latin1codec-class).

Example:

``` {.language-dart data-language="dart"}
var encoded = latin1.encode('blåbærgrød');
var decoded = latin1.decode([0x62, 0x6c, 0xe5, 0x62, 0xe6,
                             0x72, 0x67, 0x72, 0xf8, 0x64]);
```

For more information, see also [Latin1Encoder](latin1encoder-class) and
[Latin1Decoder](latin1decoder-class).

Base64
------

A [Base64Codec](base64codec-class) encodes bytes using the default
base64 alphabet, decodes using both the base64 and base64url alphabets,
does not allow invalid characters and requires padding.

The [base64](base64-constant) is the default implementation of
[Base64Codec](base64codec-class).

Example:

``` {.language-dart data-language="dart"}
var encoded = base64.encode([0x62, 0x6c, 0xc3, 0xa5, 0x62, 0xc3, 0xa6,
                             0x72, 0x67, 0x72, 0xc3, 0xb8, 0x64]);
var decoded = base64.decode('YmzDpWLDpnJncsO4ZAo=');
```

For more information, see also [Base64Encoder](base64encoder-class) and
[Base64Decoder](base64decoder-class).

Converters
----------

Converters are often used with streams to transform the data that comes
through the stream as it becomes available. The following code uses two
converters. The first is a UTF-8 decoder, which converts the data from
bytes to UTF-8 as it is read from a file, The second is an instance of
[LineSplitter](linesplitter-class), which splits the data on newline
boundaries.

``` {.language-dart data-language="dart"}
const showLineNumbers = true;
var lineNumber = 1;
var stream = File('quotes.txt').openRead();

stream.transform(utf8.decoder)
      .transform(const LineSplitter())
      .forEach((line) {
        if (showLineNumbers) {
          stdout.write('${lineNumber++} ');
        }
        stdout.writeln(line);
      });
```

See the documentation for the [Codec](codec-class) and
[Converter](converter-class) classes for information about creating your
own converters.

HTML Escape
-----------

[HtmlEscape](htmlescape-class) converter escapes characters with special
meaning in HTML. The converter finds characters that are significant in
HTML source and replaces them with corresponding HTML entities.

Custom escape modes can be created using the
[HtmlEscapeMode.HtmlEscapeMode](htmlescapemode/htmlescapemode)
constructor.

Example:

``` {.language-dart data-language="dart"}
const htmlEscapeMode = HtmlEscapeMode(
  name: 'custom',
  escapeLtGt: true,
  escapeQuot: false,
  escapeApos: false,
  escapeSlash: false,
 );

const HtmlEscape htmlEscape = HtmlEscape(htmlEscapeMode);
String unescaped = 'Text & subject';
String escaped = htmlEscape.convert(unescaped);
print(escaped); // Text &amp; subject

unescaped = '10 > 1 and 1 < 10';
escaped = htmlEscape.convert(unescaped);
print(escaped); // 10 &gt; 1 and 1 &lt; 10

unescaped = "Single-quoted: 'text'";
escaped = htmlEscape.convert(unescaped);
print(escaped); // Single-quoted: 'text'

unescaped = 'Double-quoted: "text"';
escaped = htmlEscape.convert(unescaped);
print(escaped); // Double-quoted: "text"

unescaped = 'Path: /system/';
escaped = htmlEscape.convert(unescaped);
print(escaped); // Path: /system/
```

Classes
-------

[AsciiCodec](asciicodec-class)
:   An [AsciiCodec](asciicodec-class) allows encoding strings as ASCII
    bytes and decoding ASCII bytes to strings.

[AsciiDecoder](asciidecoder-class)
:   Converts ASCII bytes to string.

[AsciiEncoder](asciiencoder-class)
:   Converts strings of only ASCII characters to bytes.

[Base64Codec](base64codec-class)
:   A [base64](https://tools.ietf.org/html/rfc4648) encoder and decoder.

[Base64Decoder](base64decoder-class)
:   Decoder for base64 encoded data.

[Base64Encoder](base64encoder-class)
:   Base64 and base64url encoding converter.

[ByteConversionSink](byteconversionsink-class)
:   The [ByteConversionSink](byteconversionsink-class) provides an
    interface for converters to efficiently transmit byte data.

[ByteConversionSinkBase](byteconversionsinkbase-class)
:   This class provides a base-class for converters that need to accept
    byte inputs.

[ChunkedConversionSink](chunkedconversionsink-class)\<T\>
:   A [ChunkedConversionSink](chunkedconversionsink-class) is used to
    transmit data more efficiently between two converters during chunked
    conversions.

[ClosableStringSink](closablestringsink-class)
:   A [ClosableStringSink](closablestringsink-class) extends the
    [StringSink](../dart-core/stringsink-class) interface by adding a
    `close` method.

[Codec](codec-class)\<S, T\>
:   A [Codec](codec-class) encodes and (if supported) decodes data.

[Converter](converter-class)\<S, T\>
:   A [Converter](converter-class) converts data from one representation
    into another.

[Encoding](encoding-class)
:   Open-ended Encoding enum.

[HtmlEscape](htmlescape-class)
:   Converter which escapes characters with special meaning in HTML.

[HtmlEscapeMode](htmlescapemode-class)
:   HTML escape modes.

[JsonCodec](jsoncodec-class)
:   A [JsonCodec](jsoncodec-class) encodes JSON objects to strings and
    decodes strings to JSON objects.

[JsonDecoder](jsondecoder-class)
:   This class parses JSON strings and builds the corresponding objects.

[JsonEncoder](jsonencoder-class)
:   This class converts JSON objects to strings.

[JsonUtf8Encoder](jsonutf8encoder-class)
:   Encoder that encodes a single object as a UTF-8 encoded JSON string.

[Latin1Codec](latin1codec-class)
:   A [Latin1Codec](latin1codec-class) encodes strings to ISO Latin-1
    (aka ISO-8859-1) bytes and decodes Latin-1 bytes to strings.

[Latin1Decoder](latin1decoder-class)
:   This class converts Latin-1 bytes (lists of unsigned 8-bit integers)
    to a string.

[Latin1Encoder](latin1encoder-class)
:   This class converts strings of only ISO Latin-1 characters to bytes.

[LineSplitter](linesplitter-class)
:   A [StreamTransformer](../dart-async/streamtransformer-class) that
    splits a [String](../dart-core/string-class) into individual lines.

[StringConversionSink](stringconversionsink-class)
:   This class provides an interface for converters to efficiently
    transmit String data.

[StringConversionSinkBase](stringconversionsinkbase-class)
:   This class provides a base-class for converters that need to accept
    String inputs.

[StringConversionSinkMixin](stringconversionsinkmixin-class)
:   This class provides a mixin for converters that need to accept
    String inputs.

[Utf8Codec](utf8codec-class)
:   A [Utf8Codec](utf8codec-class) encodes strings to utf-8 code units
    (bytes) and decodes UTF-8 code units to strings.

[Utf8Decoder](utf8decoder-class)
:   This class converts UTF-8 code units (lists of unsigned 8-bit
    integers) to a string.

[Utf8Encoder](utf8encoder-class)
:   This class converts strings to their UTF-8 code units (a list of
    unsigned 8-bit integers).

Constants
---------

[ascii](ascii-constant) → const [AsciiCodec](asciicodec-class)
:   An instance of the default implementation of the
    [AsciiCodec](asciicodec-class).
    <div>

    `AsciiCodec()`

    </div>

[base64](base64-constant) → const [Base64Codec](base64codec-class)
:   A [base64](https://tools.ietf.org/html/rfc4648) encoder and decoder.
    <div>

    `Base64Codec()`

    </div>

[base64Url](base64url-constant) → const [Base64Codec](base64codec-class)
:   A [base64url](https://tools.ietf.org/html/rfc4648) encoder and
    decoder.
    <div>

    `Base64Codec.urlSafe()`

    </div>

[htmlEscape](htmlescape-constant) → const [HtmlEscape](htmlescape-class)
:   A `String` converter that converts characters to HTML entities.
    <div>

    `HtmlEscape()`

    </div>

[json](json-constant) → const [JsonCodec](jsoncodec-class)
:   An instance of the default implementation of the
    [JsonCodec](jsoncodec-class).
    <div>

    `JsonCodec()`

    </div>

[latin1](latin1-constant) → const [Latin1Codec](latin1codec-class)
:   An instance of the default implementation of the
    [Latin1Codec](latin1codec-class).
    <div>

    `Latin1Codec()`

    </div>

[unicodeBomCharacterRune](unicodebomcharacterrune-constant) → const [int](../dart-core/int-class)
:   The Unicode Byte Order Marker (BOM) character `U+FEFF`.
    <div>

    `0xFEFF`

    </div>

[unicodeReplacementCharacterRune](unicodereplacementcharacterrune-constant) → const [int](../dart-core/int-class)
:   The Unicode Replacement character `U+FFFD` (�).
    <div>

    `0xFFFD`

    </div>

[utf8](utf8-constant) → const [Utf8Codec](utf8codec-class)
:   An instance of the default implementation of the
    [Utf8Codec](utf8codec-class).
    <div>

    `Utf8Codec()`

    </div>

Functions
---------

[base64Decode](base64decode)([String](../dart-core/string-class) source) → [Uint8List](../dart-typed_data/uint8list-class)
:   Decodes [base64](https://tools.ietf.org/html/rfc4648) or
    [base64url](https://tools.ietf.org/html/rfc4648) encoded bytes.

[base64Encode](base64encode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\> bytes) → [String](../dart-core/string-class)
:   Encodes `bytes` using [base64](https://tools.ietf.org/html/rfc4648)
    encoding.

[base64UrlEncode](base64urlencode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\> bytes) → [String](../dart-core/string-class)
:   Encodes `bytes` using
    [base64url](https://tools.ietf.org/html/rfc4648) encoding.

[jsonDecode](jsondecode)([String](../dart-core/string-class) source, {[Object](../dart-core/object-class)? reviver([Object](../dart-core/object-class)? key, [Object](../dart-core/object-class)? value)?}) → dynamic
:   Parses the string and returns the resulting Json object.

[jsonEncode](jsonencode)([Object](../dart-core/object-class)? object, {[Object](../dart-core/object-class)? toEncodable([Object](../dart-core/object-class)? nonEncodable)?}) → [String](../dart-core/string-class)
:   Converts `object` to a JSON string.

Exceptions / Errors {#exceptions}
-------------------

[JsonCyclicError](jsoncyclicerror-class)
:   Reports that an object could not be stringified due to cyclic
    references.

[JsonUnsupportedObjectError](jsonunsupportedobjecterror-class)
:   Error thrown by JSON serialization if an object cannot be
    serialized.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/dart-convert-library.html>
:::
