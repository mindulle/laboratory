\<menuitem\>
============

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.

The `<menuitem>` [HTML](../index) element represents a command that a
user is able to invoke through a popup menu. This includes context
menus, as well as menus that might be attached to a menu button.

A command can either be defined explicitly, with a textual label and
optional icon to describe its appearance, or alternatively as an
*indirect command* whose behavior is defined by a separate element.
Commands can also optionally include a checkbox or be grouped to share
radio buttons. (Menu items for indirect commands gain checkboxes or
radio buttons when defined against elements `<input type="checkbox">`
and `<input type="radio">`.)

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md); in
particular `title` can be used to describe the command, or provide usage
hints.

[`checked`](#checked) [Deprecated]

:   Boolean attribute which indicates whether the command is selected.
    May only be used when the `type` attribute is `checkbox` or `radio`.

[`command`](#command) [Deprecated]

:   Specifies the ID of a separate element, indicating a command to be
    invoked indirectly. May not be used within a menu item that also
    includes the attributes `checked`, `disabled`, `icon`, `label`,
    `radiogroup` or `type`.

[`default`](#default) [Deprecated]

:   This Boolean attribute indicates use of the same command as the
    menu\'s subject element (such as a `button` or `input`).

[`disabled`](#disabled) [Deprecated]

:   Boolean attribute which indicates that the command is not available
    in the current state. Note that `disabled` is distinct from
    `hidden`; the `disabled` attribute is appropriate in any context
    where a change in circumstances might render the command relevant.

[`icon`](#icon) [Deprecated]

:   Image URL, used to provide a picture to represent the command.

[`label`](#label)

:   The name of the command as shown to the user. Required when a
    `command` attribute is not present.

[`radiogroup`](#radiogroup) [Deprecated]

:   This attribute specifies the name of a group of commands to be
    toggled as radio buttons when selected. May only be used where the
    `type` attribute is `radio`.

[`type`](#type) [Deprecated]

:   This attribute indicates the kind of command, and can be one of
    three values.

    -   `command`: A regular command with an associated action. This is
        the missing value default.
    -   `checkbox`: Represents a command that can be toggled between two
        different states.
    -   `radio`: Represent one selection from a group of commands that
        can be toggled as radio buttons.

Examples
--------

### HTML

[html]

```html
<!-- A <div> element with a context menu -->
<div contextmenu="popup-menu">Right-click to see the adjusted context menu</div>

<menu type="context" id="popup-menu">
  <menuitem type="checkbox" checked>Checkbox</menuitem>
  <hr />
  <menuitem
    type="command"
    label="This command does nothing"
    icon="favicon-192x192.png">
    Commands don't render their contents.
  </menuitem>
  <menuitem
    type="command"
    label="This command has javascript"
    onclick="alert('command clicked')">
    Commands don't render their contents.
  </menuitem>
  <hr />
  <menuitem type="radio" radiogroup="group1">Radio Button 1</menuitem>
  <menuitem type="radio" radiogroup="group1">Radio Button 2</menuitem>
</menu>
```

### CSS

[css]

```css
div {
  width: 300px;
  height: 80px;
  background-color: lightgreen;
}

```

### Result

Technical summary
-----------------

  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  Must have a start tag and must not have an end tag.
  Permitted parents                             The [`<menu>`](menu) element, where that element is in the *popup menu* state. (If specified, the `type` attribute of the [`<menu>`](menu) element must be `popup`; if missing, the parent element of the [`<menu>`](menu) must itself be a [`<menu>`](menu) in the *popup menu* state.)
  Permitted ARIA roles                          None
  DOM interface                                 [`HTMLMenuItemElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMenuItemElement)
  --------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

Not part of any current specifications.

Browser compatibility
---------------------

See also
--------

- [HTML context menus in Firefox (Screencast and
    Code)](https://hacks.mozilla.org/2011/11/html5-context-menus-in-firefox-screencast-and-code/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menuitem>
