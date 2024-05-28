[dart:core](../../dart-core/dart-core-library){._links-link}

parseIPv6Address method
=======================

::: {.section .multi-line-signature}
[List](../list-class)\<[int](../int-class)\> parseIPv6Address(

1.  [String](../string-class) host,
2.  \[[int](../int-class) start = 0,
3.  [int](../int-class)? end\]

)
:::

Parses the `host` as an IP version 6 (IPv6) address.

Returns the address as a list of 16 bytes in network byte order (big
endian).

Throws a [FormatException](../formatexception-class) if `host` is not a
valid IPv6 address representation.

Acts on the substring from `start` to `end`. If `end` is omitted, it
defaults to the end of the string.

Some examples of IPv6 addresses:

-   `::1`
-   `FEDC:BA98:7654:3210:FEDC:BA98:7654:3210`
-   `3ffe:2a00:100:7031::1`
-   `::FFFF:129.144.52.38`
-   `2010:836B:4179::836B:4179`

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static List<int> parseIPv6Address(String host, [int start = 0, int? end]) {
  end ??= host.length;
  // An IPv6 address consists of exactly 8 parts of 1-4 hex digits, separated
  // by `:`'s, with the following exceptions:
  //
  //  - One (and only one) wildcard (`::`) may be present, representing a fill
  //    of 0's. The IPv6 `::` is thus 16 bytes of `0`.
  //  - The last two parts may be replaced by an IPv4 "dotted-quad" address.

  // Helper function for reporting a badly formatted IPv6 address.
  void error(String msg, int? position) {
    throw FormatException('Illegal IPv6 address, $msg', host, position);
  }

  // Parse a hex block.
  int parseHex(int start, int end) {
    if (end - start > 4) {
      error('an IPv6 part can only contain a maximum of 4 hex digits', start);
    }
    int value = int.parse(host.substring(start, end), radix: 16);
    if (value < 0 || value > 0xFFFF) {
      error('each part must be in the range of `0x0..0xFFFF`', start);
    }
    return value;
  }

  if (host.length < 2) error('address is too short', null);
  List<int> parts = [];
  bool wildcardSeen = false;
  // Set if seeing a ".", suggesting that there is an IPv4 address.
  bool seenDot = false;
  int partStart = start;
  // Parse all parts, except a potential last one.
  for (int i = start; i < end; i++) {
    int char = host.codeUnitAt(i);
    if (char == _COLON) {
      if (i == start) {
        // If we see a `:` in the beginning, expect wildcard.
        i++;
        if (host.codeUnitAt(i) != _COLON) {
          error('invalid start colon.', i);
        }
        partStart = i;
      }
      if (i == partStart) {
        // Wildcard. We only allow one.
        if (wildcardSeen) {
          error('only one wildcard `::` is allowed', i);
        }
        wildcardSeen = true;
        parts.add(-1);
      } else {
        // Found a single colon. Parse [partStart..i] as a hex entry.
        parts.add(parseHex(partStart, i));
      }
      partStart = i + 1;
    } else if (char == _DOT) {
      seenDot = true;
    }
  }
  if (parts.length == 0) error('too few parts', null);
  bool atEnd = (partStart == end);
  bool isLastWildcard = (parts.last == -1);
  if (atEnd && !isLastWildcard) {
    error('expected a part after last `:`', end);
  }
  if (!atEnd) {
    if (!seenDot) {
      parts.add(parseHex(partStart, end));
    } else {
      List<int> last = _parseIPv4Address(host, partStart, end);
      parts.add(last[0] << 8 | last[1]);
      parts.add(last[2] << 8 | last[3]);
    }
  }
  if (wildcardSeen) {
    if (parts.length > 7) {
      error('an address with a wildcard must have less than 7 parts', null);
    }
  } else if (parts.length != 8) {
    error('an address without a wildcard must contain exactly 8 parts', null);
  }
  List<int> bytes = Uint8List(16);
  for (int i = 0, index = 0; i < parts.length; i++) {
    int value = parts[i];
    if (value == -1) {
      int wildCardLength = 9 - parts.length;
      for (int j = 0; j < wildCardLength; j++) {
        bytes[index] = 0;
        bytes[index + 1] = 0;
        index += 2;
      }
    } else {
      bytes[index] = value >> 8;
      bytes[index + 1] = value & 0xff;
      index += 2;
    }
  }
  return bytes;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/parseIPv6Address.html>
:::
