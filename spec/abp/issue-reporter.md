# Issue reporter

1. [Bubble UI](#bubble-ui)
1. [Issue Reporter Entry](#issue-reporter-entry)
1. [Issue Reporter Comment](#issue-reporter-comment)
1. [Report Data Overlay](#report-data-overlay)
1. [Send Report](#send-report)
1. [Send Report Sent](#send-report-sent)
1. [Report Data](#report-data)
1. [Assets](#assets)

## Bubble UI

![](/res/abp/issue-reporter/bubble-ui.png)

Clicking `Report issue on this page` in the Bubble UI will open the [Entry](#issue-reporter-entry)


[Back to top of page](#header-issue-reporter)
## Issue Reporter Entry

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

### Cancel Button

Button labelled `Cancel`. Closes the *Issue Reporter* window.

### Continue Button

Button labelled `Continue`. Disabled as long as neither [False Positive Checkbox](#false-positive-checkbox) nor [False Negative Checkbox](#false-negative-checkbox) are checked. Opens [Issue Reporter Comment](#issue-reporter-comment)

### False Positive Checkbox

1. `Adblock Plus is blocking too much`
1. `Select this option if the page lacks important content, displays incorrectly or fails to function properly. You can determine whether Adblock Plus is the cause of the problem by disabling it temporarily.`

### False Negative Checbox

1. `Adblock Plus doesn't block an advertisement`
1. `Select this option if an advertisement is displayed despite Adblock Plus being enabled.`

[Back to top of page](#header-issue-reporter)
## Issue Reporter Comment

![](/res/abp/issue-reporter/issue-reporter-comment.png)

1. `Enter comment`
1. `We encourage you to enter a valid email address so that we can contact you if there are questions about your report. It will also allow us to recognize your contributions and to prioritize them higher.`
1. [Email Input](#email-input)
1. [Anonymous Checkbox](#anonymous-checkbox)
1. `The text field below allows you to enter a comment to help us understand the issue. This step is optional but recommended if the problem isn't obvious. You can also review the report data before it is sent.`
1. [Comment Textarea](#comment-textarea)
1. `Show report data` opens [Report Data Overlay](#report-data-overlay)
1. [Send Report Button](#send-report-button)

### Email Input

Input of type [email](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email) labelled `Email:`

Hightlighted red if invalid:
![](/res/abp/issue-reporter/issue-reporter-email-invalid.png)

### Anonymous Checkbox

Checkbox labelled `Anonymous submission`.

If checked disables [Email Input](#email-input):
![](/res/abp/issue-reporter/issue-reporter-email-disabled.png)

1. `We won't be able to come back to you and will likely prioritize the report lower.`

### Comment Textarea

Textarea labelled `Comment (optional):`.

### Send Report Button

Button labelled `Send report`. Start the transfer of the [Report Data](#report-data) and opens [Send Report](#send-report).

[Back to top of page](#issue-reporter)
## Report Data Overlay

![](/res/abp/issue-reporter/issue-reporter-data.png)

1. [Report Data Textarea](#report-data-textarea)
1. [Report Data Close Button](#report-data-close-button)

### Report Data Textarea

Readonly Textarea that shows the [report data](#report-data) to be sent.

### Report Data Close Button

Button labelled `Cancel` closes the [Report Data Overlay](#report-data-overlay).

[Back to top of page](#header-issue-reporter)
## Send Report

![](/res/abp/issue-reporter/issue-reporter-send.png)

1. `Send report`
1. `Please wait while Adblock Plus is submitting your report.`
1. [Done Button](#done-button) is disabled.

[Back to top of page](#header-issue-reporter)
## Send Report Sent

![](/res/abp/issue-reporter/issue-reporter-send-sent.png)

1. `Your report has been saved. You can access it at the following address:`
1. [Report Link](#report-link)
1. [Done Button](#done-button)

### Report Link

Link labeled with the *href* that links to the submitted report.

### Done Button

Button labelled `Done` that will close the *Issue Reporter* window.


## Report Data

```
<report type="false positive">
<window url="https://www.heise.de/"/>
<subscriptions>
<subscription id="https://easylist-downloads.adblockplus.org/easylist.txt" version="201712110830" lastDownloadAttempt="-5871" lastDownloadSuccess="-5871" softExpiration="85997" hardExpiration="166929" downloadStatus="synchronize_ok" disabledFilters="0"/>
<subscription id="https://easylist-downloads.adblockplus.org/exceptionrules.txt" version="201712110831" lastDownloadAttempt="-5871" lastDownloadSuccess="-5871" softExpiration="94043" hardExpiration="166929" downloadStatus="synchronize_ok" disabledFilters="0"/></subscriptions>
<adblock-plus version="3.0.1" locale="en-US"/>
<application name="Firefox" version="57.0" vendor="" userAgent="Mozilla/5.0 (X11; Linux x86_64; rv:57.0) Gecko/20100101 Firefox/57.0"/>
<platform name="Gecko" version="57.0"/></report>
```


[Back to top of page](#header-issue-reporter)
## Assets

| Name | Asset | 
|-----------|---------------|
| abp-logo.svg | ![](/res/abp/issue-reporter/assets/abp-logo.svg) |

[Back to top of page](#header-issue-reporter)
