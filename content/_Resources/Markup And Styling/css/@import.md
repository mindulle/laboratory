\@import
========

The `@import` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) is used to import style rules from other valid
stylesheets. An `@import` rule *must* be defined at the top of the
stylesheet, before any other at-rule (except [\@charset](@charset.md) and
[\@layer](@layer.md)) and style declarations, or it will be ignored.

Syntax
------

[css]

```css
@import url;
@import url layer;
@import url layer(layer-name);
@import url layer(layer-name) supports(supports-condition);
@import url layer(layer-name) supports(supports-condition) list-of-media-queries;
@import url layer(layer-name) list-of-media-queries;
@import url supports(supports-condition);
@import url supports(supports-condition) list-of-media-queries;
@import url list-of-media-queries;
```

where:

[*url*](#url)

:   Is a [`<string>`](string.md), a `<url>`, or a [`url()`](url.md) function
    representing the location of the resource to import. The URL may be
    absolute or relative.

[*list-of-media-queries*](#list-of-media-queries)

:   Is a comma-separated list of [](using_media_queries.md), which specify the
    media-dependent conditions for applying the CSS rules defined in the
    linked URL. If the browser does not support any of these queries, it
    does not load the linked resource.

[*layer-name*](#layer-name)

:   Is the name of a [cascade layer](@layer.md) into which the contents of
    the linked resource are imported.

[*supports-condition*](#supports-condition) [Experimental]

:   Indicates the feature(s) that the browser must support in order for
    the stylesheet to be imported. If the browser does not conform to
    the conditions specified in the *supports-condition*, it may not
    fetch the linked stylesheet, and even if downloaded through some
    other path, will not load it. The syntax of `supports()` is almost
    identical to that described in [`@supports`](@supports.md), and that
    topic can be used as a more complete reference.

Description
-----------

Imported rules must come before all other types of rules, except
[`@charset`](@charset.md) rules and layer creating [`@layer`](@layer.md)
statements.

[css]

```css
* {
  margin: 0;
  padding: 0;
}
/* more styles */
@import url("my-imported-styles.css");
```

As the `@import` at-rule is declared after the styles it is invalid and
hence ignored.

[css]

```css
@import url("my-imported-styles.css");
* {
  margin: 0;
  padding: 0;
}
/* more styles */
```

The `@import` rule is not a [](_Resources/Markup%20And%20Styling/css/syntax.md#nested_statements). Therefore, it cannot be used
inside [conditional group at-rules](at-rule.md#conditional_group_rules).

So that [user
agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
can avoid retrieving resources for unsupported media types, authors may
specify media-dependent import conditions. These conditional imports
specify comma-separated [](using_media_queries.md) after the URL. In the
absence of any media query, the import is not conditional on the media
used. Specifying `all` for the `list-of-media-queries` has the same
effect.

Similarly, user agents can use the `supports()` function in an `@import`
at-rule to only fetch resources if a particular feature set is (or is
not) supported. This allows authors to take advantage of recently
introduced CSS features, while providing graceful fallbacks for older
browser versions. Note that the conditions in the `supports()` function
of an `@import` at-rule can be obtained in JavaScript using
[`CSSImportRule.supportsText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSImportRule/supportsText).

The `@import` rule can also be used to create a [cascade layer](@layer.md)
by importing rules from a linked resource. Rules can also be imported
into an existing cascade layer. The `layer` keyword or the `layer()`
function is used with `@import` for this purpose. Declarations in style
rules from imported stylesheets interact with the cascade as if they
were written literally into the stylesheet at the point of the import.

Formal syntax
-------------

```
@import = 
  @import [ <url> | <string> ] [ layer | layer( <layer-name> ) ]? <import-conditions> ;  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  

<layer-name> = 
  <ident> [ '.' <ident> ]*  

<import-conditions> = 
  [ supports( [ <supports-condition> | <declaration> ] ) ]? <media-query-list>?  

<supports-condition> = 
  not <supports-in-parens>                            |
  <supports-in-parens> [ and <supports-in-parens> ]*  |
  <supports-in-parens> [ or <supports-in-parens> ]*   

<supports-in-parens> = 
  ( <supports-condition> )  |
  <supports-feature>        |
  <general-enclosed>        

<supports-feature> = 
  <supports-decl>  

<general-enclosed> = 
  [ <function-token> <any-value>? ) ]  |
  [ ( <any-value>? ) ]                 

<supports-decl> = 
  ( <declaration> )  
```

Examples
--------

### Importing CSS rules

[css]

```css
@import "custom.css";
@import url("chrome://communicator/skin/");
```

The two examples above show how to specify the *url* as a `<string>` and
as a `url()` function.

### Importing CSS rules conditional on media queries

[css]

```css
@import url("fineprint.css") print;
@import url("bluish.css") print, screen;
@import "common.css" screen;
@import url("landscape.css") screen and (orientation: landscape);
```

The `@import` rules in the above examples show media-dependent
conditions that will need to be true before the linked CSS rules are
applied. So for instance, the last `@import` rule will load the
`landscape.css` stylesheet only on a screen device in landscape
orientation.

### Importing CSS rules conditional on feature support

[css]

```css
@import url("gridy.css") supports(display: grid) screen and (max-width: 400px);
@import url("flexy.css") supports(not (display: grid) and (display: flex)) screen
  and (max-width: 400px);
```

The `@import` rules above illustrate how you might import a layout that
uses a grid if `display: grid` is supported, and otherwise imports CSS
that uses `display: flex`. While you can only have one `supports()`
statement, you can combine any number of feature checks with `not`,
`and`, and `or`, as long as you wrap each condition to be tested in
parentheses. You can also use parentheses to indicate precedence. Note
that if you just have a single declaration then you don\'t need to wrap
it in additional parenthese: this is shown in the first example above.

The examples above show support conditions using simple declaration
syntax. You can also specify CSS functions in `supports()`, and it will
evaluate to `true` if they are supported and can be evaluated on the
user-agent. For example, the code below shows an `@import` that is
conditional on both [child combinators](child_combinator.md) (`selector()`)
and the `font-tech()` function:

[css]

```css
@import url("whatever.css") supports((selector(h2 > p)) and
    (font-tech(color-COLRv1)));
```

### Importing CSS rules into a cascade layer

[css]

```css
@import "theme.css" layer(utilities);
```

In the above example, a cascade layer named `utilities` is created and
it will include rules from the imported stylesheet `theme`.

[css]

```css
@import url(headings.css) layer(default);
@import url(links.css) layer(default);

@layer default {
  audio[controls] {
    display: block;
  }
}
```

In the above example, the rules in `headings.css` and `links.css`
stylesheets cascade within the same layer as the `audio[controls]` rule.

[css]

```css
@import "theme.css" layer();
@import "style.css" layer;
```

This is an example of creating two separate unnamed cascade layers and
importing the linked rules into each one separately. A cascade layer
declared without a name is an unnamed cascade layer. Unnamed cascade
layers are finalized when created: they do not provide any means for
re-arranging or adding styles and they cannot be referenced from
outside.

Specifications
--------------

  ------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------

  [CSS Cascading and Inheritance Level 5\
  [\#
  at-import]](https://drafts.csswg.org/css-cascade-5/#at-import)

  ------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`@import`

1

12

1

5.5

3.5

1

≤37

18

4

10.1

1

1.0

`layer`

99

99

97

No

85

15.4

99

99

97

68

15.4

18.0

`supports`

No

No

115

No

No

No

No

No

115

No

No

No

See also
--------

- [`@media`](@media.md)
- [`@supports`](@supports.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@import>
