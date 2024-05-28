[dart:core](../dart-core/dart-core-library){._links-link}

RegExpMatch class
=================

A regular expression match.

Regular expression matches are [Match](match-class)es, but also include
the ability to retrieve the names for any named capture groups and to
retrieve matches for named capture groups by name instead of their
index.

Example:

``` {.language-dart data-language="dart"}
const pattern =
    r'^\[(?<Time>\s*((?<hour>\d+)):((?<minute>\d+))\.((?<second>\d+)))\]'
    r'\s(?<Message>\s*(.*)$)';

final regExp = RegExp(
  pattern,
  multiLine: true,
);

const multilineText = '[00:13.37] This is a first message.\n'
    '[01:15.57] This is a second message.\n';

RegExpMatch regExpMatch = regExp.firstMatch(multilineText)!;
print(regExpMatch.groupNames.join('-')); // hour-minute-second-Time-Message.
final time = regExpMatch.namedGroup('Time'); // 00:13.37
final hour = regExpMatch.namedGroup('hour'); // 00
final minute = regExpMatch.namedGroup('minute'); // 13
final second = regExpMatch.namedGroup('second'); // 37
final message =
    regExpMatch.namedGroup('Message'); // This is a first message.
final date = regExpMatch.namedGroup('Date'); // Undefined `Date`, throws.

Iterable<RegExpMatch> matches = regExp.allMatches(multilineText);
for (final m in matches) {
  print(m.namedGroup('Time'));
  print(m.namedGroup('Message'));
  // 00:13.37
  // This is a first message.
  // 01:15.57
  // This is a second message.
}
```

Implemented types

:   -   [Match](match-class)

Annotations

:   -   \@Since(\"2.3\")

Constructors
------------

[RegExpMatch](regexpmatch/regexpmatch)()

Properties {#instance-properties}
----------

[end](match/end) → [int](int-class)

::: {.features}
read-only, inherited
:::

The index in the string after the last character of the match.

[groupCount](match/groupcount) → [int](int-class)

::: {.features}
read-only, inherited
:::

Returns the number of captured groups in the match.

[groupNames](regexpmatch/groupnames) →
[Iterable](iterable-class)\<[String](string-class)\>

::: {.features}
read-only
:::

The names of the captured groups in the match.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[input](match/input) → [String](string-class)

::: {.features}
read-only, inherited
:::

The string on which this match was computed.

[pattern](match/pattern) → [Pattern](pattern-class)

::: {.features}
read-only, inherited
:::

The pattern used to search in [input](match/input).

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[start](match/start) → [int](int-class)

::: {.features}
read-only, inherited
:::

The index in the string where the match starts.

Methods {#instance-methods}
-------

[group](match/group)([int](int-class) group) → [String](string-class)?

::: {.features}
inherited
:::

The string matched by the given [group](match/group).

[groups](match/groups)([List](list-class)\<[int](int-class)\>
groupIndices) → [List](list-class)\<[String](string-class)?\>

::: {.features}
inherited
:::

A list of the groups with the given indices.

[namedGroup](regexpmatch/namedgroup)([String](string-class) name) →
[String](string-class)?

The string matched by the group named `name`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator \[\]](match/operator_get)([int](int-class) group) →
[String](string-class)?

::: {.features}
inherited
:::

The string matched by the given `group`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExpMatch-class.html>
:::
