[dart:core](../dart-core/dart-core-library){._links-link}

Match class
===========

A result from searching within a string.

A `Match` or an [Iterable](iterable-class) of `Match` objects is
returned from the [Pattern](pattern-class) matching methods
([Pattern.allMatches](pattern/allmatches) and
[Pattern.matchAsPrefix](pattern/matchasprefix)).

The following example finds all matches of a [RegExp](regexp-class) in a
[String](string-class) and iterates through the returned iterable of
`Match` objects.

``` {.language-dart data-language="dart"}
final regExp = RegExp(r'(\w+)');
const string = 'Parse my string';
final matches = regExp.allMatches(string);
for (final m in matches) {
  String match = m[0]!;
  print(match);
}
```

The output of the example is:

``` {.language-dart data-language="dart"}
Parse
my
string
```

Some patterns, regular expressions in particular, may record substrings
that were part of the matching. These are called *groups* in the `Match`
object. Some patterns may never have any groups, and their matches
always have zero [groupCount](match/groupcount).

Implementers

:   -   [RegExpMatch](regexpmatch-class)

Constructors
------------

[Match](match/match)()

Properties {#instance-properties}
----------

[end](match/end) → [int](int-class)

::: {.features}
read-only
:::

The index in the string after the last character of the match.

[groupCount](match/groupcount) → [int](int-class)

::: {.features}
read-only
:::

Returns the number of captured groups in the match.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[input](match/input) → [String](string-class)

::: {.features}
read-only
:::

The string on which this match was computed.

[pattern](match/pattern) → [Pattern](pattern-class)

::: {.features}
read-only
:::

The pattern used to search in [input](match/input).

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[start](match/start) → [int](int-class)

::: {.features}
read-only
:::

The index in the string where the match starts.

Methods {#instance-methods}
-------

[group](match/group)([int](int-class) group) → [String](string-class)?

The string matched by the given [group](match/group).

[groups](match/groups)([List](list-class)\<[int](int-class)\>
groupIndices) → [List](list-class)\<[String](string-class)?\>

A list of the groups with the given indices.

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

The string matched by the given `group`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Match-class.html>
:::
