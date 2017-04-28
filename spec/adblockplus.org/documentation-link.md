Documentation link (/redirect)
========================

The Documentation link page is used by the our adblocking products to redirect the user to a url specified by a parameter. This way we can update the url without having to update the product.

**Url**:

```
/redirect
```

|Parameter|Description|
|---------|-----------|
|link|the name of the link (refer to the table below for valid link names)|
|lang|the language the url should be displayed in if possible (defaults to en if the target is not available in requested language or the language has been ommitted)|



|Name|Locale[1]|GeoIp[2]|target url|
|----|------|-----|----------|
|reporter_connect_issue|-|`/forum/?`|
|reporter_other_link|-|-|`/forum/?`|
|chrome_support|-|-|`/forum/viewforum.php?f=10?`|
|opera_support|-|-|`/forum/viewforum.php?f=14?`|
|safari_support|-|-|`/forum/viewforum.php?f=18?`|
|edge_support|-|-|`/forum/viewforum.php?f=27?`|
|knownIssuesChrome_filterstorage|-|-|`/forum/viewtopic.php?t=23597?`|
|adblock_browser_android_beta_community|-|-|`https://plus.google.com/communities/104936844759781288661?`|
|`^adblock_browser_promotion_\d$`|-|-|`https://adblockplus.org/adblock-browser`|
|adblock_browser_android_support|`*`|-|`https://adblockbrowser.org/$lang/android-support/?`|
|adblock_browser_android_faq|`*`|-|`https://adblockbrowser.org/$lang/android-support/faq?`|
|adblock_browser_ios_support|-|-|`https://adblockbrowser.org/en/ios-support/?`|
|adblock_browser_android_store|-|`*`|`https://play.google.com/store/apps/details?id=org.adblockplus.browser`|
|adblock_browser_android_store|-|`cn`|`https://downloads.adblockplus.org/adblockbrowser-1.1.0-arm.apk`|
|adblock_browser_ios_store|-|-|`https://geo.itunes.apple.com/us/app/adblock-browser-best-ad-blocker/id1015653330?mt=8?`|
|adblock_browser_android_download|-|-|`https://downloads.adblockplus.org/adblockbrowser-1.1.0-arm.apk`|
|adblock_plus_safari_ios_support|-|-|`/forum/viewforum.php?f=26?`|
|adblock_plus_safari_ios_store|-|-|`https://itunes.apple.com/app/adblock-plus-abp/id1028871868?`|
|adblock_plus_sbrowser_store|-|-|`https://play.google.com/store/apps/details?id=org.adblockplus.adblockplussbrowser?`|
|releases|-|-|`/releases?`|
|social_facebook|-|-|`https://www.facebook.com/adblockplus?`|
|social_gplus|-|-|`https://www.google.com/+AdblockPlus?`|
|social_renren|-|-|`http://www.renren.com/601651969?`|
|social_twitter|-|-|`https://twitter.com/adblockplus?`|
|social_weibo|-|-|`http://e.weibo.com/adblockplus/?`|
|`^share-`|IF APL|-|`https://share.adblockplus.org/$lang/?`|
|uninstalled|IF APL|-|`https://adblockplus.org/uninstalled?link=uninstalled`|
|gettingStarted|IF APL|-|`https://adblockplus.org/getting_started`|
|faq|IF APL|-|`https://adblockplus.org/faq`|
|filterdoc|IF APL|-|`https://adblockplus.org/filters`|
|subscriptions|IF APL|-|`https://adblockplus.org/subscriptions`|
|reporter_privacy|IF APL|-|`https://adblockplus.org/privacy#abp_issue_reporter`|
|privacy|IF APL|-|`https://adblockplus.org/privacy`|
|contribute|IF APL|-|`https://adblockplus.org/contribute`|
|donate|IF APL|-|`https://adblockplus.org/donate`|
|acceptable_ads|IF APL|-|`https://adblockplus.org/acceptable-ads`|
|acceptable_ads_criteria|IF APL|-|`https://adblockplus.org/acceptable-ads#criteria`|
|contributors|IF APL|-|`https://adblockplus.org/contributors`|

[1] ***Locale***: *-* ignore locale, `*` apply for all unspecified locales, `xy` apply only for specified locale, *IF APL* (If applicable) redirect to locale specific document if applicable

[2] ***GeoIp***: *-*: ignore GeoIp, `*` apply for all unspecified GeoIp, `xy` apply only for specified GeoIp
