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
|firefox_support|-|-|`/forum/viewforum.php?f=1?`|
|chrome_support|-|-|`/forum/viewforum.php?f=10?`|
|opera_support|-|-|`/forum/viewforum.php?f=14?`|
|safari_support|-|-|`/forum/viewforum.php?f=18?`|
|edge_support|-|-|`/forum/viewforum.php?f=27?`|
|knownIssuesChrome_filterstorage|-|-|`/forum/viewtopic.php?t=23597?`|
|adblock_browser_android_beta_community|-|-|`https://plus.google.com/communities/104936844759781288661?`|
|`^adblock_browser_promotion_\d$`|-|-|`https://adblockplus.org/adblock-browser`|
|adblock_browser_android_support|-|-|`/forum/viewforum.php?f=24?`|
|adblock_browser_android_faq|-|-|`/forum/viewforum.php?f=24?`|
|adblock_browser_ios_support|-|-|`/forum/viewforum.php?f=25?`|
|adblock_browser_android_store|-|`*`|`https://play.google.com/store/apps/details?id=org.adblockplus.browser`|
|adblock_browser_android_store|-|`cn`|`https://downloads.adblockplus.org/adblockbrowser-1.1.0-arm.apk`|
|adblock_browser_ios_store|-|-|`https://geo.itunes.apple.com/us/app/adblock-browser-best-ad-blocker/id1015653330?mt=8?`|
|adblock_browser_android_download|-|-|`https://downloads.adblockplus.org/adblockbrowser-1.1.0-arm.apk`|
|adblock_browser_website|-|-|`https://adblockplus.org/adblock-browser`|
|adblock_plus_safari_ios_support|-|-|`/forum/viewforum.php?f=26?`|
|adblock_plus_safari_ios_store|-|-|`https://itunes.apple.com/app/adblock-plus-abp/id1028871868?`|
|adblock_plus_sbrowser_store|-|-|`https://play.google.com/store/apps/details?id=org.adblockplus.adblockplussbrowser?`|
|adblock_plus_chrome_dnt|-|-|`https://support.google.com/chrome/answer/2790761`|
|adblock_plus_firefox_dnt|-|-|`https://www.mozilla.org/en-US/firefox/dnt/`|
|adblock_plus_opera_dnt|-|-|`http://help.opera.com/Windows/12.10/en/notrack.html`|
|adblock_plus_edge_dnt|-|-|`https://privacy.microsoft.com/en-us/windows-10-microsoft-edge-and-privacy`|
|adblock_plus_report_bug|-|-|`https://adblockplus.org/bugs#reporting`|
|adblock_plus_report_ad|-|-|`https://forums.lanik.us/viewforum.php?f=62`|
|adblock_plus_report_issue|`en`|-|`https://forums.lanik.us/viewforum.php?f=64`|
|adblock_plus_report_issue|`id`|-|`https://forums.lanik.us/viewforum.php?f=94`|
|adblock_plus_report_issue|`nl`|-|`https://forums.lanik.us/viewforum.php?f=100`|
|adblock_plus_report_issue|`de`|-|`https://forums.lanik.us/viewforum.php?f=90`|
|adblock_plus_report_issue|`it`|-|`https://forums.lanik.us/viewforum.php?f=96`|
|adblock_plus_report_issue|`es`|-|`https://forums.lanik.us/viewforum.php?f=103`|
|adblock_plus_report_issue|`lt`|-|`https://forums.lanik.us/viewtopic.php?f=101`|
|adblock_plus_report_issue|`lv`|-|`https://forums.lanik.us/viewforum.php?f=99`|
|adblock_plus_report_issue|`ar`|-|`https://forums.lanik.us/viewforum.php?f=98`|
|adblock_plus_report_issue|`fr`|-|`https://forums.lanik.us/viewforum.php?f=91`|
|adblock_plus_report_issue|`ru`|-|`https://forums.lanik.us/viewforum.php?f=102`|
|adblock_plus_report_issue|`*`|-|`https://forums.lanik.us/viewforum.php?f=64`|
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
|language_subscription|IF APL|-|`https://adblockplus.org/getting_started#subscription`|
|reporter_privacy|IF APL|-|`https://adblockplus.org/privacy#issue-reporter`|
|privacy|IF APL|-|`https://adblockplus.org/privacy`|
|contribute|IF APL|-|`https://adblockplus.org/contribute`|
|donate|IF APL|-|`https://adblockplus.org/donate`|
|acceptable_ads|IF APL|-|`https://adblockplus.org/acceptable-ads`|
|acceptable_ads_criteria|IF APL|-|`https://adblockplus.org/acceptable-ads#criteria`|
|privacy_friendly_ads|IF APL|-|`https://adblockplus.org/acceptable-ads#privacy-friendly-acceptable-ads`|
|contributors|IF APL|-|`https://adblockplus.org/contributors`|
|whitelist|IF APL|-|`https://adblockplus.org/faq_basics#disable`|
|adblock_plus|IF APL|-|`https://adblockplus.org`|
|eyeo|IF APL|-|`https://eyeo.com`|
|developer|-|-|`https://adblockplus.org/forum/viewforum.php?f=4`|
|help_center|-|-|`http://help.eyeo.com`|

[1] ***Locale***: *-* ignore locale, `*` apply for all unspecified locales, `xy` apply only for specified locale, *IF APL* (If applicable) redirect to locale specific document if applicable

[2] ***GeoIp***: *-*: ignore GeoIp, `*` apply for all unspecified GeoIp, `xy` apply only for specified GeoIp
