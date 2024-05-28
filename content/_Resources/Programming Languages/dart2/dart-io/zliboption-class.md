[dart:io](../dart-io/dart-io-library){._links-link}

ZLibOption class
================

Exposes ZLib options for input parameters.

See <http://www.zlib.net/manual.html> for more documentation.

Constructors
------------

[ZLibOption](zliboption/zliboption)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Constants
---------

[defaultLevel](zliboption/defaultlevel-constant) → const [int](../dart-core/int-class)
:   Default value for [ZLibCodec.level](zlibcodec/level) and
    [ZLibEncoder.level](zlibencoder/level).
    <div>

    `6`

    </div>

[defaultMemLevel](zliboption/defaultmemlevel-constant) → const [int](../dart-core/int-class)
:   Default value for [ZLibCodec.memLevel](zlibcodec/memlevel) and
    [ZLibEncoder.memLevel](zlibencoder/memlevel).
    <div>

    `8`

    </div>

[defaultWindowBits](zliboption/defaultwindowbits-constant) → const [int](../dart-core/int-class)
:   Default value for [ZLibCodec.windowBits](zlibcodec/windowbits),
    [ZLibEncoder.windowBits](zlibencoder/windowbits) and
    [ZLibDecoder.windowBits](zlibdecoder/windowbits).
    <div>

    `15`

    </div>

[maxLevel](zliboption/maxlevel-constant) → const [int](../dart-core/int-class)
:   Maximal value for [ZLibCodec.level](zlibcodec/level) and
    [ZLibEncoder.level](zlibencoder/level)
    <div>

    `9`

    </div>

[maxMemLevel](zliboption/maxmemlevel-constant) → const [int](../dart-core/int-class)
:   Maximal value for [ZLibCodec.memLevel](zlibcodec/memlevel) and
    [ZLibEncoder.memLevel](zlibencoder/memlevel).
    <div>

    `9`

    </div>

[maxWindowBits](zliboption/maxwindowbits-constant) → const [int](../dart-core/int-class)
:   Maximal value for [ZLibCodec.windowBits](zlibcodec/windowbits),
    [ZLibEncoder.windowBits](zlibencoder/windowbits) and
    [ZLibDecoder.windowBits](zlibdecoder/windowbits).
    <div>

    `15`

    </div>

[minLevel](zliboption/minlevel-constant) → const [int](../dart-core/int-class)
:   Minimal value for [ZLibCodec.level](zlibcodec/level) and
    [ZLibEncoder.level](zlibencoder/level).
    <div>

    `-1`

    </div>

[minMemLevel](zliboption/minmemlevel-constant) → const [int](../dart-core/int-class)
:   Minimal value for [ZLibCodec.memLevel](zlibcodec/memlevel) and
    [ZLibEncoder.memLevel](zlibencoder/memlevel).
    <div>

    `1`

    </div>

[minWindowBits](zliboption/minwindowbits-constant) → const [int](../dart-core/int-class)
:   Minimal value for [ZLibCodec.windowBits](zlibcodec/windowbits),
    [ZLibEncoder.windowBits](zlibencoder/windowbits) and
    [ZLibDecoder.windowBits](zlibdecoder/windowbits).
    <div>

    `8`

    </div>

[strategyDefault](zliboption/strategydefault-constant) → const [int](../dart-core/int-class)
:   Recommended strategy for normal data
    <div>

    `0`

    </div>

[strategyFiltered](zliboption/strategyfiltered-constant) → const [int](../dart-core/int-class)
:   Recommended strategy for data produced by a filter (or predictor)
    <div>

    `1`

    </div>

[strategyFixed](zliboption/strategyfixed-constant) → const [int](../dart-core/int-class)
:   This strategy prevents the use of dynamic Huffman codes, allowing
    for a simpler decoder
    <div>

    `4`

    </div>

[strategyHuffmanOnly](zliboption/strategyhuffmanonly-constant) → const [int](../dart-core/int-class)
:   Use this strategy to force Huffman encoding only (no string match)
    <div>

    `2`

    </div>

[strategyRle](zliboption/strategyrle-constant) → const [int](../dart-core/int-class)
:   Use this strategy to limit match distances to one (run-length
    encoding)
    <div>

    `3`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibOption-class.html>
:::
