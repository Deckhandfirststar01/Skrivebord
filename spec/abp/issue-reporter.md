# Issue reporter

1. [Bubble UI](#bubble-ui)
1. [Issue Reporter Tab](#issue-reporter-tab)
    1. [Issue Reporter Entry](#issue-reporter-entry)
    1. [Issue Reporter Comment](#issue-reporter-comment)
    1. [Report Data Overlay](#report-data-overlay)
    1. [Send Report](#send-report)
    1. [Send Report Sent](#send-report-sent)
1. [Data gathering tab](#data-gathering-tab)
1. [Report Data](#report-data)
1. [Assets](#assets)

## Bubble UI

![](/res/abp/issue-reporter/bubble-ui.png)

Clicking `Report issue on this page` in the Bubble UI will:

1. Open the [Issue Reporter Tab](#issue-reporter-tab) in a new active tab.
1. Open the page the user had opened in the previously active tab in the [Data gathering tab](#data-gathering-tab). The [Data gathering tab](#data-gathering-tab) should be opened in a new background tab to record all [Requests](#requests) and [Filters](#filters) to include in the [Report Data](#report-data).
1. Display a message within a banner on the Issue reporter (on all steps) `**Note**: An additional tab will temporarily open so the page you are on won't be affected by the Issue Reporter.`, the banner should be closeable via the *X* icon.

![](/res/abp/issue-reporter/select-issue.jpg)

[Back to top of page](#issue-reporter)

## Issue reporter tab

### Issue Reporter Entry

![](/res/abp/issue-reporter/issue-reporter-entry.png)

1. `Adblock **Plus**` 
1. *abp-logo.svg*, alt=`Adblock Plus logo`
1. `Issue reporter`
1. `Select issue type`
1. `This window will guide you through the steps required for the submission of an Adblock Plus issue report. First, please select the type of issue that you are experiencing on this page:`
1. [False Positive Checkbox](#false-positive-checkbox)
1. [False Negative Checkbox](#false-negative-checkbox)
1. `Privacy policy` opens [Documentation link](/spec/abp/prefs.md#documentation-link) `%LINK%=reporter_privacy` in a new tab
1. [Cancel Button](#cancel-button)
1. [Continue Button](#continue-button)

#### Cancel Button

Button labelled `Cancel`. Closes the [Issue Reporter Tab](#issue-reporter-tab) and the [Data gathering tab](#data-gathering-tab).

#### Continue Button

Button labelled `Continue`. Disabled as long as neither [False Positive Checkbox](#false-positive-checkbox) nor [False Negative Checkbox](#false-negative-checkbox) are checked. Opens [Issue Reporter Comment](#issue-reporter-comment)

### False Positive Checkbox

1. `Adblock Plus is blocking too much`
1. `Select this option if the page lacks important content, displays incorrectly or fails to function properly. You can determine whether Adblock Plus is the cause of the problem by disabling it temporarily.`

### False Negative Checbox

1. `Adblock Plus doesn't block an advertisement`
1. `Select this option if an advertisement is displayed despite Adblock Plus being enabled.`

[Back to top of page](#issue-reporter)
### Issue Reporter Comment

![](/res/abp/issue-reporter/issue-reporter-comment.png)

1. `Enter comment`
1. `We encourage you to enter a valid email address so that we can contact you if there are questions about your report. It will also allow us to recognize your contributions and to prioritize them higher.`
1. [Email Input](#email-input)
1. [Anonymous Checkbox](#anonymous-checkbox)
1. `The text field below allows you to enter a comment to help us understand the issue. This step is optional but recommended if the problem isn't obvious. You can also review the report data before it is sent.`
1. [Comment Textarea](#comment-textarea)
1. `Show report data` opens [Report Data Overlay](#report-data-overlay)
1. [Show report data link](#show-report-data-link)
1. [Send Report Button](#send-report-button)

#### Email Input

Input of type [email](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email) labelled `Email:`

Hightlighted red if invalid:
![](/res/abp/issue-reporter/issue-reporter-email-invalid.png)

#### Anonymous Checkbox

Checkbox labelled `I would like to submit my issue anonymously`.

If checked disables [Email Input](#email-input):
![](/res/abp/issue-reporter/issue-reporter-email-disabled.png)

#### Comment Textarea

Textarea labelled `Please help us better understand the issue by leaving a comment below.`.

#### Show report data link

Link labelled `Show report data`.

Is disabled until [Data gathering tab](#data-gathering-tab) has [loaded](https://developer.mozilla.org/en-US/docs/Web/Events/load) or the [Minimum data gethering time](#minimum-data-gethering-time) is elapsed.

Closes the [Data gathering tab](#data-gathering-tab) and opens the [Report Data Overlay](#report-data-overlay).


#### Send Report Button

Button labelled `Send report`.

Is disabled until [Data gathering tab](#data-gathering-tab) has [loaded](https://developer.mozilla.org/en-US/docs/Web/Events/load) or the [Minimum data gethering time](#minimum-data-gethering-time) is elapsed.

Closes the [Data gathering tab](#data-gathering-tab), starts the transfer of the [Report Data](#report-data) and opens [Send Report](#send-report).


[Back to top of page](#issue-reporter)
### Report Data Overlay

![](/res/abp/issue-reporter/issue-reporter-data.png)

1. [Report Data Textarea](#report-data-textarea)
1. [Report Data Close Button](#report-data-close-button)

#### Report Data Textarea

Readonly Textarea that shows the [report data](#report-data) to be sent.

#### Report Data Close Button

Button labelled `Cancel` closes the [Report Data Overlay](#report-data-overlay).

[Back to top of page](#issue-reporter)
### Send Report

![](/res/abp/issue-reporter/issue-reporter-send.png)

1. `Send report`
1. `Please wait while Adblock Plus is submitting your report.`
1. [Done Button](#done-button) is disabled.

[Back to top of page](#issue-reporter)
### Send Report Sent

![](/res/abp/issue-reporter/issue-reporter-send-sent.png)

1. `Your report has been saved. You can access it at the following address:`
1. [Report Link](#report-link)
1. [Done Button](#done-button)

#### Report Link

Link labeled with the *href* that links to the submitted report.

#### Done Button

Button labelled `Done` that will close the [Issue Reporter Tab](#issue-reporter-tab).

### Data gathering tab

When the issue reporter is opened, the page for which an issue is being reported will be opened in the [Data gathering tab](#data-gathering-tab).

The [Data gathering tab](#data-gathering-tab) will gather all [Requests](#requests) and all [Filters](#filters) for as long as the tab is opened.

Once the page has loaded ([load](https://developer.mozilla.org/en-US/docs/Web/Events/load)) or the [minumum data gathering time](#minumum-data-gathering-time) has elapsed the [Data gethering tab](#data-gathering-tab) will scroll to the same viewport the user was using in the original page when he opnend the [Issue Reporter](#issue-reporter).

#### Minimum data gethering time

We'll gather [Requests](#requests) and all [Filters](#filters) for at least 5 seconds.

## Report Data


### Report

The root element of the report with the type of the report: *false positive* if the user selected the [False Positive Checkbox](#false-positive-checkbox) or *false negative* if the user selected the [False Negative Checkbox](#false-negative-checkbox).

```xml
<report type="false positive">
...
</report>
```

#### Main URL

The url of the main window (*mainURL*) the user opened the issue reporter on.

```xml
<window url="https://www.heise.de/"/>
```

#### Subscriptions

A [subscription](#subscription) for each filter list the user has subscribed to.

```xml
<subscriptions>
...
</subscriptions>
```

##### Subscription

The subscription consisting of:

|Attribute|Value|
|---------|-----|
|*subscriptionVersion*|*version*|The version (YYYYMMDDhhmm) of the filter list|
|*lastDownloadAttempt*|Number of seconds between now and the last attempt download attempt|
|*lastDownloadSuccess*|Number of seconds between now and the last attempt download success|
|*softExpiration*|The soft expiration date of the filter list. (The softExpiration represents the number of seconds between the next potential download attempt and now. It may be postponed if user is offline.)|
|*hardExpiration*|The hard expiration date of the filter list. (The hardExpiration represents the number of seconds between the next potential download attempt in case download got postponed for too long and now.)|
|*downloadStatus*|The download status of a filter list|
|*disabledFilters*|The number of disabled filters in this filter list|

```xml
<subscription
    id="https://easylist-downloads.adblockplus.org/easylist.txt"
    version="201712110830"
    lastDownloadAttempt="-5871"
    lastDownloadSuccess="-5871"
    softExpiration="85997"
    hardExpiration="166929"
    downloadStatus="synchronize_ok"
    disabledFilters="0" />
```

#### AdblockPlus

Information about AdblockPlus:

|Attribute|Value|
|---------|-----|
|*version*|Version of the ABP Product|
|*locale*|Locale the user is using the ABP Product in|

```xml
<adblock-plus version="3.0.1" locale="en-US"/>
```

#### Application

Information about the Application (i.e. Browser) the user is using ABP in:

|Attribute|Value|
|---------|-----|
|*name*|Name of the application (i.e. Browser) the user is using ABP in|
|*version*|Version of the application (i.e. Browser) the user is using ABP in|
|*vendor*|Name of the vendor of the application (i.e. Browser) the user is using ABP in|
|*userAgent*|UserAgent of the application (i.e. Browser) the user is using ABP in|

```xml
<application
    name="Firefox"
    version="57.0"
    vendor=""
    userAgent="Mozilla/5.0 (X11; Linux x86_64; rv:57.0) Gecko/20100101 Firefox/57.0"/>
```

#### Platform

Information about the Platform of the Application (i.e. Browser) the user is using ABP in:

|Attribute|Value|
|---------|-----|
|*name*|Name of the Platform of the application (i.e. Browser) the user is usign ABP in|
|*version*|Version the Platform of the application (i.e. Browser) the user is using ABP in|

```xml
<platform name="Gecko" version="57.0"/>
```

#### Requests

A [request](#request) for each request the main window made.

```xml
<requests>
...
</requests>
```

##### Request

|Attribute|Value|
|---------|-----|
|*location*|The location of a resource used by the page the issue report is issued for (Ommitted in case of type=ELEMHIDE).|
|*type*|The type of the request, see [here](https://hg.adblockplus.org/adblockpluscore/file/9ad72e008065/lib/filterClasses.js#l798) for a list of all supported types|
|*docDomain*|The domain of the document the resource is used on|
|*thirdParty*|Whether or not the resource is a third party resource (location doesn't match docDomain)|
|*count*|The number of times the request has been encountered|
|*filter*|The text of the filter in case a filter hit was recorded. Omitted if no filter applies to this request|

```xml
<request
    location="https://www.heise.de/js/mobile-deflect.min.js?ea85dfed7d6dc25326c5"
    type="SCRIPT"
    docDomain="www.heise.de"
    thirdParty="false"
    count="2" />
<request
    location="https://securepubads.g.doubleclick.net/gpt/pubads_impl_170.js"
    type="SCRIPT"
    docDomain="www.heise.de"
    thirdParty="true"
    count="1"
    filter="@@||g.doubleclick.net/gpt/pubads_impl_$script,domain=~kizi.com"/>
<request
    type="ELEMHIDE"
    docDomain="www.heise.de"
    thirdParty="false"
    count="1"
    filter="##.wingadblock"/>
```

#### Filters

A [filter](#filter) for each filter hit in the main window.

```xml
<filters>
...
</filters>
```

##### Filter

|Attribute|Value|
|---------|-----|
|*text*|The text of an applied filter|
|*subscriptions*|Space separated list of subscriptionURLs|
|*hitCount*|The number of filter hits that where registered for this filter on the [Data gathering tab](#data-gathering-tab)|

```xml
<filter
    text="@@||g.doubleclick.net/gpt/pubads_impl_$script,domain=~kizi.com"
    subscriptions="https://easylist-downloads.adblockplus.org/exceptionrules.txt"
    hitCount="2"/>
<filter
    text="##.wingadblock"
    subscriptions="https://easylist-downloads.adblockplus.org/easylist.txt"
    hitCount="1"/>
```

[Back to top of page](#issue-reporter)
## Assets

| Name | Asset | 
|-----------|---------------|
| abp-logo.svg | ![](/res/abp/issue-reporter/assets/abp-logo.svg) |

[Back to top of page](#issue-reporter)
