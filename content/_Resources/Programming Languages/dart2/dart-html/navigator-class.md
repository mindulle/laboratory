[dart:html](../dart-html/dart-html-library){._links-link}

Navigator class
===============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NavigatorConcurrentHardware](navigatorconcurrenthardware-class)
    -   Navigator

Implemented types

:   -   [NavigatorCookies](navigatorcookies-class)
    -   [NavigatorID](navigatorid-class)
    -   [NavigatorLanguage](navigatorlanguage-class)
    -   [NavigatorOnLine](navigatoronline-class)
    -   [NavigatorAutomationInformation](navigatorautomationinformation-class)

Annotations

:   -   \@Native(\"Navigator\")

Properties {#instance-properties}
----------

[appCodeName](navigator/appcodename) →
[String](../dart-core/string-class)

::: {.features}
read-only, override
:::

[appName](navigator/appname) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

[appVersion](navigator/appversion) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

[budget](navigator/budget) → \_BudgetService?

::: {.features}
read-only
:::

[clipboard](navigator/clipboard) → \_Clipboard?

::: {.features}
read-only
:::

[connection](navigator/connection) →
[NetworkInformation](networkinformation-class)?

::: {.features}
read-only
:::

[cookieEnabled](navigator/cookieenabled) →
[bool](../dart-core/bool-class)?

::: {.features}
\@Unstable(), read-only, override
:::

[credentials](navigator/credentials) →
[CredentialsContainer](credentialscontainer-class)?

::: {.features}
read-only
:::

[dartEnabled](navigator/dartenabled) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, override
:::

[deviceMemory](navigator/devicememory) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[doNotTrack](navigator/donottrack) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[geolocation](navigator/geolocation) → [Geolocation](geolocation-class)

::: {.features}
\@Unstable(), read-only
:::

[hardwareConcurrency](navigatorconcurrenthardware/hardwareconcurrency) →
[int](../dart-core/int-class)?

::: {.features}
read-only, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[language](navigator/language) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

[languages](navigator/languages) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?

::: {.features}
read-only, override
:::

[maxTouchPoints](navigator/maxtouchpoints) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[mediaCapabilities](navigator/mediacapabilities) →
[MediaCapabilities](mediacapabilities-class)?

::: {.features}
read-only
:::

[mediaDevices](navigator/mediadevices) →
[MediaDevices](mediadevices-class)?

::: {.features}
read-only
:::

[mediaSession](navigator/mediasession) →
[MediaSession](mediasession-class)?

::: {.features}
read-only
:::

[mimeTypes](navigator/mimetypes) → [MimeTypeArray](mimetypearray-class)?

::: {.features}
read-only
:::

[nfc](navigator/nfc) → \_NFC?

::: {.features}
read-only
:::

[onLine](navigator/online) → [bool](../dart-core/bool-class)?

::: {.features}
\@Unstable(), read-only, override
:::

[permissions](navigator/permissions) → [Permissions](permissions-class)?

::: {.features}
read-only
:::

[persistentStorage](navigator/persistentstorage) →
[DeprecatedStorageQuota](deprecatedstoragequota-class)?

::: {.features}
\@JSName(\'webkitPersistentStorage\'),
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only
:::

[platform](navigator/platform) → [String](../dart-core/string-class)?

::: {.features}
read-only, override
:::

[presentation](navigator/presentation) →
[Presentation](presentation-class)?

::: {.features}
read-only
:::

[product](navigator/product) → [String](../dart-core/string-class)

::: {.features}
\@Unstable(), read-only, override
:::

[productSub](navigator/productsub) →
[String](../dart-core/string-class)?

::: {.features}
\@Unstable(), read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[serviceWorker](navigator/serviceworker) →
[ServiceWorkerContainer](serviceworkercontainer-class)?

::: {.features}
read-only
:::

[storage](navigator/storage) → [StorageManager](storagemanager-class)?

::: {.features}
read-only
:::

[temporaryStorage](navigator/temporarystorage) →
[DeprecatedStorageQuota](deprecatedstoragequota-class)?

::: {.features}
\@JSName(\'webkitTemporaryStorage\'),
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only
:::

[userAgent](navigator/useragent) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

[vendor](navigator/vendor) → [String](../dart-core/string-class)

::: {.features}
\@Unstable(), read-only
:::

[vendorSub](navigator/vendorsub) → [String](../dart-core/string-class)

::: {.features}
\@Unstable(), read-only
:::

[vr](navigator/vr) → [VR](vr-class)?

::: {.features}
read-only
:::

[webdriver](navigator/webdriver) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, override
:::

Methods {#instance-methods}
-------

[cancelKeyboardLock](navigator/cancelkeyboardlock)() → void

[getBattery](navigator/getbattery)() →
[Future](../dart-async/future-class)

[getGamepads](navigator/getgamepads)() →
[List](../dart-core/list-class)\<[Gamepad](gamepad-class)?\>

[getInstalledRelatedApps](navigator/getinstalledrelatedapps)() →
[Future](../dart-async/future-class)\<[RelatedApplication](relatedapplication-class)\>

[getUserMedia](navigator/getusermedia)({dynamic audio = false, dynamic
video = false}) →
[Future](../dart-async/future-class)\<[MediaStream](mediastream-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME)
:::

Gets a stream (video and or audio) from the local computer.

[getVRDisplays](navigator/getvrdisplays)() →
[Future](../dart-async/future-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[registerProtocolHandler](navigator/registerprotocolhandler)([String](../dart-core/string-class)
scheme, [String](../dart-core/string-class) url,
[String](../dart-core/string-class) title) → void

::: {.features}
\@Unstable()
:::

[requestKeyboardLock](navigator/requestkeyboardlock)(\[[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?
keyCodes\]) → [Future](../dart-async/future-class)

[requestMediaKeySystemAccess](navigator/requestmediakeysystemaccess)([String](../dart-core/string-class)
keySystem,
[List](../dart-core/list-class)\<[Map](../dart-core/map-class)\>
supportedConfigurations) → [Future](../dart-async/future-class)

[requestMidiAccess](navigator/requestmidiaccess)(\[[Map](../dart-core/map-class)?
options\]) → [Future](../dart-async/future-class)

::: {.features}
\@JSName(\'requestMIDIAccess\')
:::

[sendBeacon](navigator/sendbeacon)([String](../dart-core/string-class)
url, [Object](../dart-core/object-class)? data) →
[bool](../dart-core/bool-class)

[share](navigator/share)(\[[Map](../dart-core/map-class)? data\]) →
[Future](../dart-async/future-class)

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Navigator-class.html>
:::
