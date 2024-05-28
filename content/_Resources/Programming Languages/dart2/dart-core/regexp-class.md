[dart:core](../dart-core/dart-core-library){._links-link}

RegExp class
============

A regular expression pattern.

Regular expressions are [Pattern](pattern-class)s, and can as such be
used to match strings or parts of strings.

Dart regular expressions have the same syntax and semantics as
JavaScript regular expressions. See
[ecma-international.org/ecma-262/9.0/\#sec-regexp-regular-expression-objects](https://ecma-international.org/ecma-262/9.0/#sec-regexp-regular-expression-objects)
for the specification of JavaScript regular expressions.

The [firstMatch](regexp/firstmatch) method is the main implementation
method that applies a regular expression to a string and returns the
first [RegExpMatch](regexpmatch-class). All other methods in
[RegExp](regexp-class) can be build from that.

The following example finds the first match of a regular expression in a
string.

``` {.language-dart data-language="dart"}
RegExp exp = RegExp(r'(\w+)');
String str = 'Parse my string';
RegExpMatch? match = exp.firstMatch(str);
print(match![0]); // "Parse"
```

Use [allMatches](regexp/allmatches) to look for all matches of a regular
expression in a string.

The following example finds all matches of a regular expression in a
string.

``` {.language-dart data-language="dart"}
RegExp exp = RegExp(r'(\w+)');
String str = 'Parse my string';
Iterable<RegExpMatch> matches = exp.allMatches(str);
for (final m in matches) {
  print(m[0]);
}
```

The output of the example is:

``` {.language-dart data-language="dart"}
Parse
my
string
```

Note the use of a *raw string* (a string prefixed with `r`) in the
example above. Use a raw string to treat each character in a string as a
literal character.

Implemented types

:   -   [Pattern](pattern-class)

Constructors
------------

[RegExp](regexp/regexp)([String](string-class) source,
{[bool](bool-class) multiLine = false, [bool](bool-class) caseSensitive
= true, \@Since(\"2.4\") [bool](bool-class) unicode = false,
\@Since(\"2.4\") [bool](bool-class) dotAll = false})

::: {.constructor-modifier .features}
factory
:::

Constructs a regular expression.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isCaseSensitive](regexp/iscasesensitive) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this regular expression is case sensitive.

[isDotAll](regexp/isdotall) → [bool](bool-class)

::: {.features}
\@Since(\"2.4\"), read-only
:::

Whether \".\" in this regular expression matches line terminators.

[isMultiLine](regexp/ismultiline) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this regular expression matches multiple lines.

[isUnicode](regexp/isunicode) → [bool](bool-class)

::: {.features}
\@Since(\"2.4\"), read-only
:::

Whether this regular expression is in Unicode mode.

[pattern](regexp/pattern) → [String](string-class)

::: {.features}
read-only
:::

The source regular expression string used to create this `RegExp`.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[allMatches](regexp/allmatches)([String](string-class) input,
\[[int](int-class) start = 0\]) →
[Iterable](iterable-class)\<[RegExpMatch](regexpmatch-class)\>

::: {.features}
override
:::

Matches this pattern against the string repeatedly.

[firstMatch](regexp/firstmatch)([String](string-class) input) →
[RegExpMatch](regexpmatch-class)?

Finds the first match of the regular expression in the string `input`.

[hasMatch](regexp/hasmatch)([String](string-class) input) →
[bool](bool-class)

Whether the regular expression has a match in the string `input`.

[matchAsPrefix](pattern/matchasprefix)([String](string-class) string,
\[[int](int-class) start = 0\]) → [Match](match-class)?

::: {.features}
inherited
:::

Matches this pattern against the start of `string`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[stringMatch](regexp/stringmatch)([String](string-class) input) →
[String](string-class)?

The substring of the first match of this regular expression in `input`.

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

Static Methods
--------------

[escape](regexp/escape)([String](string-class) text) → [String](string-class)
:   Creates regular expression syntax that matches `text`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp-class.html>
:::
