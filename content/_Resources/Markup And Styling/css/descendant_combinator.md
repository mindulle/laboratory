Descendant combinator
=====================

The **descendant combinator** --- typically represented by a single
space (\" \") character --- combines two selectors such that elements
matched by the second selector are selected if they have an ancestor
(parent, parent\'s parent, parent\'s parent\'s parent, etc.) element
matching the first selector. Selectors that utilize a descendant
combinator are called *descendant selectors*.

[css]

```css
/* List items that are descendants of the "my-things" list */
ul.my-things li {
  margin: 2em;
}
```

The descendant combinator is technically one or more
[CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) white space
characters --- the space character and/or one of four control
characters: carriage return, form feed, new line, and tab characters ---
between two selectors in the absence of another combinator.
Additionally, the white space characters of which the combinator is
comprised may contain any number of CSS comments.

Syntax
------

[css]

```css
selector1 selector2 {
  /* property declarations */
}
```

Examples
--------

### CSS

[css]

```css
li {
  list-style-type: disc;
}

li li {
  list-style-type: circle;
}
```

### HTML

[html]

```html
<ul>
  <li>
    <div>Item 1</div>
    <ul>
      <li>Subitem A</li>
      <li>Subitem B</li>
    </ul>
  </li>
  <li>
    <div>Item 2</div>
    <ul>
      <li>Subitem A</li>
      <li>Subitem B</li>
    </ul>
  </li>
</ul>
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  descendant-combinators]](https://drafts.csswg.org/selectors/#descendant-combinators)

  ----------------------------------------------------------------------------------------------

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

`Descendant_combinator`

1Since Chrome 61, `>>>` is aliased to this selector [since its use as
the \'shadow-piercing descendant combinator\' was
deprecated](https://developers.google.com/web/updates/2017/06/chrome-60-deprecations#make_shadow-piercing_descendant_combinator_behave_like_descendent_combinator).

12

1

3

3.5

1

4.4Since Chrome 61, `>>>` is aliased to this selector [since its use as
the \'shadow-piercing descendant combinator\' was
deprecated](https://developers.google.com/web/updates/2017/06/chrome-60-deprecations#make_shadow-piercing_descendant_combinator_behave_like_descendent_combinator).

18Since Chrome 61, `>>>` is aliased to this selector [since its use as
the \'shadow-piercing descendant combinator\' was
deprecated](https://developers.google.com/web/updates/2017/06/chrome-60-deprecations#make_shadow-piercing_descendant_combinator_behave_like_descendent_combinator).

4

10.1

1

1.0Since Samsung Internet 8.0, `>>>` is aliased to this selector [since
its use as the \'shadow-piercing descendant combinator\' was
deprecated](https://developers.google.com/web/updates/2017/06/chrome-60-deprecations#make_shadow-piercing_descendant_combinator_behave_like_descendent_combinator).

`two_greater_than_syntax`

No

No

No

No

No

10--11.1

No

No

No

No

10--11.3

No

See also
--------

- [Child combinator](child_combinator.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator>
