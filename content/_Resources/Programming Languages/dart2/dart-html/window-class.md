[dart:html](../dart-html/dart-html-library){._links-link}

Window class
============

Top-level container for the current browser tab or window.

In a web browser, each window has a [Window](window-class) object, but
within the context of a script, this object represents only the current
window. Each other window, tab, and iframe has its own
[Window](window-class) object.

Each window contains a [Document](document-class) object, which contains
all of the window\'s content.

Use the top-level `window` object to access the current window. For
example:

``` {.language-dart data-language="dart"}
// Draw a scene when the window repaints.
drawScene(num delta) {...}
window.animationFrame.then(drawScene);.

// Write to the console.
window.console.log('Jinkies!');
window.console.error('Jeepers!');
```

**Note:** This class represents only the current window, while
[WindowBase](windowbase-class) is a representation of any window,
including other tabs, windows, and frames.

See also
--------

-   [WindowBase](windowbase-class)

Other resources
---------------

-   [DOM Window](https://developer.mozilla.org/en-US/docs/DOM/window)
    from MDN.
-   [Window](http://www.w3.org/TR/Window/) from the W3C.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   Window

Implemented types

:   -   [GlobalEventHandlers](globaleventhandlers-class)
    -   [WindowBase64](windowbase64-class)
    -   [WindowEventHandlers](windoweventhandlers-class)
    -   [WindowBase](windowbase-class)

Annotations

:   -   \@Native(\"Window,DOMWindow\")

Properties {#instance-properties}
----------

[animationFrame](window/animationframe) →
[Future](../dart-async/future-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

Returns a Future that completes just before the window is about to
repaint so the user can draw an animation frame.

[animationWorklet](window/animationworklet) → \_Worklet?

::: {.features}
read-only
:::

[applicationCache](window/applicationcache) →
[ApplicationCache](applicationcache-class)?

::: {.features}
read-only
:::

The application cache for this window.

[audioWorklet](window/audioworklet) → \_Worklet?

::: {.features}
read-only
:::

[caches](window/caches) → [CacheStorage](cachestorage-class)?

::: {.features}
read-only
:::

[closed](window/closed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, override
:::

Indicates whether this window has been closed.

[console](window/console) → [Console](console-class)

::: {.features}
read-only
:::

The debugging console for this window.

[cookieStore](window/cookiestore) → [CookieStore](cookiestore-class)?

::: {.features}
read-only
:::

[crypto](window/crypto) → [Crypto](crypto-class)?

::: {.features}
read-only
:::

Entrypoint for the browser\'s cryptographic functions.

[customElements](window/customelements) →
[CustomElementRegistry](customelementregistry-class)?

::: {.features}
read-only
:::

[defaultStatus](window/defaultstatus) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

*Deprecated*.

[defaultstatus](window/defaultstatus) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

*Deprecated*.

[devicePixelRatio](window/devicepixelratio) →
[num](../dart-core/num-class)

::: {.features}
read-only
:::

The ratio between physical pixels and logical CSS pixels.

[document](window/document) → [Document](document-class)

::: {.features}
read-only
:::

The newest document in this window.

[external](window/external) → [External](external-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[history](window/history) → [History](history-class)

::: {.features}
read-only, override
:::

The current session history for this window\'s newest document.

[indexedDB](window/indexeddb) →
[IdbFactory](../dart-indexed_db/idbfactory-class)?

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'23.0\'),
\@SupportedBrowser(SupportedBrowser.FIREFOX, \'15.0\'),
\@SupportedBrowser(SupportedBrowser.IE, \'10.0\'), read-only
:::

Gets an instance of the Indexed DB factory to being using Indexed DB.

[innerHeight](window/innerheight) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

The height of the viewport including scrollbars.

[innerWidth](window/innerwidth) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

The width of the viewport including scrollbars.

[isSecureContext](window/issecurecontext) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[localStorage](window/localstorage) → [Storage](storage-class)

::: {.features}
read-only
:::

Storage for this window that persists across sessions.

[location](window/location) ↔ [Location](location-class)

::: {.features}
read / write, override-getter
:::

The current location of this window.

[locationbar](window/locationbar) →
[BarProp](barprop-class){.deprecated}?

::: {.features}
read-only
:::

This window\'s location bar, which displays the URL.

[menubar](window/menubar) → [BarProp](barprop-class){.deprecated}?

::: {.features}
read-only
:::

This window\'s menu bar, which displays menu commands.

[name](window/name) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

The name of this window.

[navigator](window/navigator) → [Navigator](navigator-class)

::: {.features}
read-only
:::

The user agent accessing this window.

[offscreenBuffering](window/offscreenbuffering) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

Whether objects are drawn offscreen before being displayed.

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAbort](window/onabort) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `abort` events handled by this [Window](window-class).

[onAnimationEnd](window/onanimationend) →
[Stream](../dart-async/stream-class)\<[AnimationEvent](animationevent-class)\>

::: {.features}
read-only
:::

Stream of `animationend` events handled by this [Window](window-class).

[onAnimationIteration](window/onanimationiteration) →
[Stream](../dart-async/stream-class)\<[AnimationEvent](animationevent-class)\>

::: {.features}
read-only
:::

Stream of `animationiteration` events handled by this
[Window](window-class).

[onAnimationStart](window/onanimationstart) →
[Stream](../dart-async/stream-class)\<[AnimationEvent](animationevent-class)\>

::: {.features}
read-only
:::

Stream of `animationstart` events handled by this
[Window](window-class).

[onBeforeUnload](window/onbeforeunload) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `beforeunload` events handled by this [Window](window-class).

[onBlur](window/onblur) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `blur` events handled by this [Window](window-class).

[onCanPlay](window/oncanplay) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onCanPlayThrough](window/oncanplaythrough) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onChange](window/onchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `change` events handled by this [Window](window-class).

[onClick](window/onclick) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `click` events handled by this [Window](window-class).

[onContentLoaded](window/oncontentloaded) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `contentloaded` events handled by this [Window](window-class).

[onContextMenu](window/oncontextmenu) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `contextmenu` events handled by this [Window](window-class).

[onDeviceMotion](window/ondevicemotion) →
[Stream](../dart-async/stream-class)\<[DeviceMotionEvent](devicemotionevent-class)\>

::: {.features}
read-only
:::

Stream of `devicemotion` events handled by this [Window](window-class).

[onDeviceOrientation](window/ondeviceorientation) →
[Stream](../dart-async/stream-class)\<[DeviceOrientationEvent](deviceorientationevent-class)\>

::: {.features}
read-only
:::

Stream of `deviceorientation` events handled by this
[Window](window-class).

[onDoubleClick](window/ondoubleclick) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
\@DomName(\'Window.ondblclick\'), read-only, override
:::

Stream of `doubleclick` events handled by this [Window](window-class).

[onDrag](window/ondrag) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `drag` events handled by this [Window](window-class).

[onDragEnd](window/ondragend) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `dragend` events handled by this [Window](window-class).

[onDragEnter](window/ondragenter) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `dragenter` events handled by this [Window](window-class).

[onDragLeave](window/ondragleave) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `dragleave` events handled by this [Window](window-class).

[onDragOver](window/ondragover) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `dragover` events handled by this [Window](window-class).

[onDragStart](window/ondragstart) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `dragstart` events handled by this [Window](window-class).

[onDrop](window/ondrop) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `drop` events handled by this [Window](window-class).

[onDurationChange](window/ondurationchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onEmptied](window/onemptied) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onEnded](window/onended) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onError](window/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `error` events handled by this [Window](window-class).

[onFocus](window/onfocus) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `focus` events handled by this [Window](window-class).

[onHashChange](window/onhashchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `hashchange` events handled by this [Window](window-class).

[onInput](window/oninput) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `input` events handled by this [Window](window-class).

[onInvalid](window/oninvalid) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `invalid` events handled by this [Window](window-class).

[onKeyDown](window/onkeydown) →
[Stream](../dart-async/stream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, override
:::

Stream of `keydown` events handled by this [Window](window-class).

[onKeyPress](window/onkeypress) →
[Stream](../dart-async/stream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, override
:::

Stream of `keypress` events handled by this [Window](window-class).

[onKeyUp](window/onkeyup) →
[Stream](../dart-async/stream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, override
:::

Stream of `keyup` events handled by this [Window](window-class).

[onLoad](window/onload) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `load` events handled by this [Window](window-class).

[onLoadedData](window/onloadeddata) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onLoadedMetadata](window/onloadedmetadata) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onLoadStart](window/onloadstart) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onMessage](window/onmessage) →
[Stream](../dart-async/stream-class)\<[MessageEvent](messageevent-class)\>

::: {.features}
read-only, override
:::

Stream of `message` events handled by this [Window](window-class).

[onMouseDown](window/onmousedown) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mousedown` events handled by this [Window](window-class).

[onMouseEnter](window/onmouseenter) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseenter` events handled by this [Window](window-class).

[onMouseLeave](window/onmouseleave) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseleave` events handled by this [Window](window-class).

[onMouseMove](window/onmousemove) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mousemove` events handled by this [Window](window-class).

[onMouseOut](window/onmouseout) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseout` events handled by this [Window](window-class).

[onMouseOver](window/onmouseover) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseover` events handled by this [Window](window-class).

[onMouseUp](window/onmouseup) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseup` events handled by this [Window](window-class).

[onMouseWheel](window/onmousewheel) →
[Stream](../dart-async/stream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mousewheel` events handled by this [Window](window-class).

[onOffline](window/onoffline) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `offline` events handled by this [Window](window-class).

[onOnline](window/ononline) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `online` events handled by this [Window](window-class).

[onPageHide](window/onpagehide) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `pagehide` events handled by this [Window](window-class).

[onPageShow](window/onpageshow) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `pageshow` events handled by this [Window](window-class).

[onPause](window/onpause) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onPlay](window/onplay) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onPlaying](window/onplaying) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onPopState](window/onpopstate) →
[Stream](../dart-async/stream-class)\<[PopStateEvent](popstateevent-class)\>

::: {.features}
read-only, override
:::

Stream of `popstate` events handled by this [Window](window-class).

[onProgress](window/onprogress) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onRateChange](window/onratechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onReset](window/onreset) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `reset` events handled by this [Window](window-class).

[onResize](window/onresize) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `resize` events handled by this [Window](window-class).

[onScroll](window/onscroll) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `scroll` events handled by this [Window](window-class).

[onSearch](window/onsearch) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `search` events handled by this [Window](window-class).

[onSeeked](window/onseeked) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onSeeking](window/onseeking) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onSelect](window/onselect) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `select` events handled by this [Window](window-class).

[onStalled](window/onstalled) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onStorage](window/onstorage) →
[Stream](../dart-async/stream-class)\<[StorageEvent](storageevent-class)\>

::: {.features}
read-only, override
:::

Stream of `storage` events handled by this [Window](window-class).

[onSubmit](window/onsubmit) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `submit` events handled by this [Window](window-class).

[onSuspend](window/onsuspend) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onTimeUpdate](window/ontimeupdate) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onTouchCancel](window/ontouchcancel) →
[Stream](../dart-async/stream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, override
:::

Stream of `touchcancel` events handled by this [Window](window-class).

[onTouchEnd](window/ontouchend) →
[Stream](../dart-async/stream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, override
:::

Stream of `touchend` events handled by this [Window](window-class).

[onTouchMove](window/ontouchmove) →
[Stream](../dart-async/stream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, override
:::

Stream of `touchmove` events handled by this [Window](window-class).

[onTouchStart](window/ontouchstart) →
[Stream](../dart-async/stream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, override
:::

Stream of `touchstart` events handled by this [Window](window-class).

[onTransitionEnd](window/ontransitionend) →
[Stream](../dart-async/stream-class)\<[TransitionEvent](transitionevent-class)\>

::: {.features}
read-only
:::

Stream of `transitionend` events handled by this [Window](window-class).

[onUnload](window/onunload) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `unload` events handled by this [Window](window-class).

[onVolumeChange](window/onvolumechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onWaiting](window/onwaiting) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onWheel](window/onwheel) →
[Stream](../dart-async/stream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only, override
:::

Stream of `wheel` events handled by this [Window](window-class).

[opener](window/opener) ↔ [WindowBase](windowbase-class)?

::: {.features}
read / write, override-getter
:::

A reference to the window that opened this one.

[orientation](window/orientation) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[origin](window/origin) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[outerHeight](window/outerheight) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The height of this window including all user interface elements.

[outerWidth](window/outerwidth) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The width of the window including all user interface elements.

[pageXOffset](window/pagexoffset) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[pageYOffset](window/pageyoffset) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[parent](window/parent) → [WindowBase](windowbase-class)?

::: {.features}
read-only, override
:::

A reference to the parent of this window.

[performance](window/performance) → [Performance](performance-class)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE), read-only
:::

Timing and navigation data for this window.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[screen](window/screen) → [Screen](screen-class)?

::: {.features}
read-only
:::

Information about the screen displaying this window.

[screenLeft](window/screenleft) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

The distance from the left side of the screen to the left side of this
window.

[screenTop](window/screentop) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

The distance from the top of the screen to the top of this window.

[screenX](window/screenx) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

The distance from the left side of the screen to the mouse pointer.

[screenY](window/screeny) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

The distance from the top of the screen to the mouse pointer.

[scrollbars](window/scrollbars) → [BarProp](barprop-class){.deprecated}?

::: {.features}
read-only
:::

This window\'s scroll bars.

[scrollX](window/scrollx) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The distance this window has been scrolled horizontally.

[scrollY](window/scrolly) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The distance this window has been scrolled vertically.

[self](window/self) → [WindowBase](windowbase-class)?

::: {.features}
read-only
:::

The current window.

[sessionStorage](window/sessionstorage) → [Storage](storage-class)

::: {.features}
read-only
:::

Storage for this window that is cleared when this session ends.

[speechSynthesis](window/speechsynthesis) →
[SpeechSynthesis](speechsynthesis-class)?

::: {.features}
read-only
:::

Access to speech synthesis in the browser.

[status](window/status) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

*Deprecated*.

[statusbar](window/statusbar) → [BarProp](barprop-class){.deprecated}?

::: {.features}
read-only
:::

This window\'s status bar.

[styleMedia](window/stylemedia) → [StyleMedia](stylemedia-class)?

::: {.features}
read-only
:::

Access to CSS media queries.

[toolbar](window/toolbar) → [BarProp](barprop-class){.deprecated}?

::: {.features}
read-only
:::

This window\'s tool bar.

[top](window/top) → [WindowBase](windowbase-class)?

::: {.features}
read-only, override
:::

A reference to the topmost window in the window hierarchy.

[visualViewport](window/visualviewport) →
[VisualViewport](visualviewport-class)?

::: {.features}
read-only
:::

[window](window/window) → [WindowBase](windowbase-class)?

::: {.features}
read-only
:::

The current window.

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[alert](window/alert)(\[[String](../dart-core/string-class)? message\])
→ void

Displays a modal alert to the user.

[atob](window/atob)([String](../dart-core/string-class) atob) →
[String](../dart-core/string-class)

::: {.features}
override
:::

[btoa](window/btoa)([String](../dart-core/string-class) btoa) →
[String](../dart-core/string-class)

::: {.features}
override
:::

[cancelAnimationFrame](window/cancelanimationframe)([int](../dart-core/int-class)
id) → void

Cancels an animation frame request.

[cancelIdleCallback](window/cancelidlecallback)([int](../dart-core/int-class)
handle) → void

[close](window/close)() → void

::: {.features}
override
:::

Closes the window.

[confirm](window/confirm)(\[[String](../dart-core/string-class)?
message\]) → [bool](../dart-core/bool-class)

Displays a modal OK/Cancel prompt to the user.

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[fetch](window/fetch)(dynamic input, \[[Map](../dart-core/map-class)?
init\]) → [Future](../dart-async/future-class)

[find](window/find)([String](../dart-core/string-class)? string,
[bool](../dart-core/bool-class)? caseSensitive,
[bool](../dart-core/bool-class)? backwards,
[bool](../dart-core/bool-class)? wrap, [bool](../dart-core/bool-class)?
wholeWord, [bool](../dart-core/bool-class)? searchInFrames,
[bool](../dart-core/bool-class)? showDialog) →
[bool](../dart-core/bool-class)

Finds text in this window.

[getComputedStyleMap](window/getcomputedstylemap)([Element](element-class)
element, [String](../dart-core/string-class)? pseudoElement) →
[StylePropertyMapReadonly](stylepropertymapreadonly-class)

[getMatchedCssRules](window/getmatchedcssrules)([Element](element-class)?
element, [String](../dart-core/string-class)? pseudoElement) →
[List](../dart-core/list-class)\<[CssRule](cssrule-class)\>

::: {.features}
\@JSName(\'getMatchedCSSRules\'), \@Returns(\'\_CssRuleList\'),
\@Creates(\'\_CssRuleList\')
:::

Returns all CSS rules that apply to the element\'s pseudo-element.

[getSelection](window/getselection)() → [Selection](selection-class)?

Returns the currently selected text.

[matchMedia](window/matchmedia)([String](../dart-core/string-class)
query) → [MediaQueryList](mediaquerylist-class)

Returns a list of media queries for the given query string.

[moveBy](window/moveby)([int](../dart-core/int-class) x,
[int](../dart-core/int-class) y) → void

Moves this window.

[moveTo](window/moveto)([Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>
p) → void

Moves this window to a specific position.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[open](window/open)([String](../dart-core/string-class) url,
[String](../dart-core/string-class) name,
\[[String](../dart-core/string-class)? options\]) →
[WindowBase](windowbase-class)

Opens a new window.

[postMessage](window/postmessage)(dynamic message,
[String](../dart-core/string-class) targetOrigin,
\[[List](../dart-core/list-class)\<[Object](../dart-core/object-class)\>?
transfer\]) → void

::: {.features}
override
:::

Sends a cross-origin message.

[print](window/print)() → void

Opens the print dialog for this window.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[requestAnimationFrame](window/requestanimationframe)([FrameRequestCallback](framerequestcallback)
callback) → [int](../dart-core/int-class)

Called to draw an animation frame and then request the window to repaint
after `callback` has finished (creating the animation).

[requestFileSystem](window/requestfilesystem)([int](../dart-core/int-class)
size, {[bool](../dart-core/bool-class) persistent = false}) →
[Future](../dart-async/future-class)\<[FileSystem](filesystem-class)\>

Access a sandboxed file system of `size` bytes.

[requestIdleCallback](window/requestidlecallback)([IdleRequestCallback](idlerequestcallback)
callback, \[[Map](../dart-core/map-class)? options\]) →
[int](../dart-core/int-class)

[resizeBy](window/resizeby)([int](../dart-core/int-class) x,
[int](../dart-core/int-class) y) → void

Resizes this window by an offset.

[resizeTo](window/resizeto)([int](../dart-core/int-class) x,
[int](../dart-core/int-class) y) → void

Resizes this window to a specific width and height.

[resolveLocalFileSystemUrl](window/resolvelocalfilesystemurl)([String](../dart-core/string-class)
url) → [Future](../dart-async/future-class)\<[Entry](entry-class)\>

::: {.features}
\@JSName(\'webkitResolveLocalFileSystemURL\'),
\@SupportedBrowser(SupportedBrowser.CHROME)
:::

Asynchronously retrieves a local filesystem entry.

[scroll](window/scroll)(\[dynamic options\_OR\_x, dynamic y,
[Map](../dart-core/map-class)? scrollOptions\]) → void

Scrolls the page horizontally and vertically to a specific point.

[scrollBy](window/scrollby)(\[dynamic options\_OR\_x, dynamic y,
[Map](../dart-core/map-class)? scrollOptions\]) → void

Scrolls the page horizontally and vertically by an offset.

[scrollTo](window/scrollto)(\[dynamic options\_OR\_x, dynamic y,
[Map](../dart-core/map-class)? scrollOptions\]) → void

Scrolls the page horizontally and vertically to a specific point.

[stop](window/stop)() → void

Stops the window from loading.

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

Static Properties
-----------------

[supportsPointConversions](window/supportspointconversions) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

convertPointFromNodeToPage and convertPointFromPageToNode are removed.
see <http://dev.w3.org/csswg/cssom-view/#geometry>

Constants
---------

[animationEndEvent](window/animationendevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[AnimationEvent](animationevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

Static factory designed to expose `animationend` events to event
handlers that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<AnimationEvent>('webkitAnimationEnd')`

</div>

[animationIterationEvent](window/animationiterationevent-constant) →
const
[EventStreamProvider](eventstreamprovider-class)\<[AnimationEvent](animationevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

Static factory designed to expose `animationiteration` events to event
handlers that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<AnimationEvent>('webkitAnimationIteration')`

</div>

[animationStartEvent](window/animationstartevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[AnimationEvent](animationevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

Static factory designed to expose `animationstart` events to event
handlers that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<AnimationEvent>('webkitAnimationStart')`

</div>

[beforeUnloadEvent](window/beforeunloadevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[BeforeUnloadEvent](beforeunloadevent-class)\>

Static factory designed to expose `beforeunload` events to event
handlers that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider('beforeunload')`

</div>

[contentLoadedEvent](window/contentloadedevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `contentloaded` events to event
handlers that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<Event>('DOMContentLoaded')`

</div>

[deviceMotionEvent](window/devicemotionevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[DeviceMotionEvent](devicemotionevent-class)\>

Static factory designed to expose `devicemotion` events to event
handlers that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<DeviceMotionEvent>('devicemotion')`

</div>

[deviceOrientationEvent](window/deviceorientationevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[DeviceOrientationEvent](deviceorientationevent-class)\>

Static factory designed to expose `deviceorientation` events to event
handlers that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<DeviceOrientationEvent>('deviceorientation')`

</div>

[hashChangeEvent](window/hashchangeevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `hashchange` events to event handlers
that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<Event>('hashchange')`

</div>

[loadStartEvent](window/loadstartevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('loadstart')`

</div>

[messageEvent](window/messageevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MessageEvent](messageevent-class)\>

Static factory designed to expose `message` events to event handlers
that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<MessageEvent>('message')`

</div>

[offlineEvent](window/offlineevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `offline` events to event handlers
that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<Event>('offline')`

</div>

[onlineEvent](window/onlineevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `online` events to event handlers that
are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<Event>('online')`

</div>

[pageHideEvent](window/pagehideevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `pagehide` events to event handlers
that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<Event>('pagehide')`

</div>

[pageShowEvent](window/pageshowevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `pageshow` events to event handlers
that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<Event>('pageshow')`

</div>

[PERSISTENT](window/persistent-constant) → const
[int](../dart-core/int-class)

Indicates that file system data cannot be cleared unless given user
permission.

<div>

`1`

</div>

[popStateEvent](window/popstateevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[PopStateEvent](popstateevent-class)\>

Static factory designed to expose `popstate` events to event handlers
that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<PopStateEvent>('popstate')`

</div>

[progressEvent](window/progressevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('progress')`

</div>

[storageEvent](window/storageevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[StorageEvent](storageevent-class)\>

Static factory designed to expose `storage` events to event handlers
that are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<StorageEvent>('storage')`

</div>

[TEMPORARY](window/temporary-constant) → const
[int](../dart-core/int-class)

Indicates that file system data can be cleared at any time.

<div>

`0`

</div>

[unloadEvent](window/unloadevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `unload` events to event handlers that
are not necessarily instances of [Window](window-class).

<div>

`const EventStreamProvider<Event>('unload')`

</div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window-class.html>
:::
