Preferences
===========

***NOTE***: Because most of the preferences are border line implementation details only the ones that are needed to for other parts of the specification are described here. See [lib/prefs.js](https://hg.adblockplus.org/adblockpluschrome/file/tip/lib/prefs.js) for a complete list of preferences.

documentation_link
------------------

A url that is used to link to abp related urls without having to include the actual url in the extension. This way we can update the url without having to update the product. For valid `%LINK%` parameters see [adblockplus.org/redirect](/spec/adblockplus.org/documentation-link.md), `%LANG%` is replaced with the current locale.

`https://adblockplus.org/redirect?link=%LINK%&lang=%LANG%`


additional_subscriptions
------------------------

Additional subscriptions are subscriptions that are added through group policies and cannot be removed See <https://issues.adblockplus.org/ticket/3801>
