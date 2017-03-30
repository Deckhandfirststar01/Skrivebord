Options Page
============

Options page for the ABP Browser extension.

The options page is used to change various options of the ABP browser extension.

1. [Whitelist tab](#whitelist-tab)
1. [Advanced tab](#advanced-tab)
1. [Additional subscriptions](#additional-subscriptions)

## General requirements

### Bidirectionailty

Any change of state will be immediately reflected in the options page regardless
of where and how the change was made, so that the options page always reflects
the current state of the extension.

- If the user opens the option page more than once and makes changes to either
  of them, the change will be reflected in any of them and not just the one
  the change was made. 
- If a change to the state was made through other means e.g. auto update of
  filter list subscriptions, it will be reflected immediately in every instance
  of the options page.

### WCAG

Should implement the following [WCAG 2.0 Guidelines](http://www.w3.org/TR/2008/REC-WCAG20-20081211/):

- 2.1 Keyboard Accessible

## Navigation

Implement <https://www.w3.org/TR/2016/WD-wai-aria-practices-1.1-20161214/#tabpanel>

Whitelist tab
-------------

### Whitelist tab empty

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/whitelisted-websites.jpg' width='888px' />

<!-- TODO: make numbers in screenshot match numbered list below -->

1. [Whitelist tab headline](#whitelist-tab-headline)
1. [Whitelist tab description](#whitelist-tab-description)
1. [Add whitelisted domain textinput](#add-whitelisted-domain-textinput)
1. [Add whitelisted domain button](#add-whitelisted-domain-button)
1. [Add whitelisted domain error message](#add-whitelisted-domain-error-message)
1. [Empty Whitelist placeholder](#empty-whitelist-placeholder)

#### Whitelist tab headline

Headline for the [Whitelist tab](#whitelist-tab) `Whitelisted websites`

#### Whitelist tab description

Description for the [Whitelist tab](#whitelist-tab).

```
You’ve turned off ad blocking on these websites. You will see ads on these websites. [Learn more](link to Help Centre article about whitelisting)
```

***TODO***: Add link to Help centre article

#### Add whitelisted domain textinput

Textinput to enter domains to be added to the whitelist.
 - Auto-focus when the [Whitelist tab](#whitelist-tab) is first loaded
 - Validate as you type

| Condition | Error message |
|-----------|---------------|
| Invalid hostname | `Not a valid hostname` |
| Duplicate hostname | `Website is already whitelisted` |


> Whats a valid hostname? <https://tools.ietf.org/html/rfc3986#section-3.2.2>

#### Add whitelisted domain button

Button to submit [Textinput A](#textinput-a).
 - Labelled `Add website`
 - Will only be active if [Add whitelisted domain textinput](#add-whitelisted-domain-textinput) is not empty and valid.

If clicked whitelist domain and show [Whitelisted domain added notification](#whitelisted-domain-added-notification).

> A whitelisted domain is an exception rule filter for a certain host.

#### Add whitelisted domain error message

Shows an error message if [Add whitelisted domain textinput](#add-whitelisted-domain-textinput) doesn't validate.

See [Add whitelisted domain textinput](#add-whitelisted-domain-textinput) for more details.

#### Empty Whitelist placeholder

Placeholder text shown as long as there are no whitelisted domains.

 - `You aren't whitelisting any websites yet.`
 - `Websites you trust and want to allow ads on will be shown here.`

### Whitelist tab populated

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/whitelisted-websites-populated.jpg' width='888px' />

1. [List of whitelisted domains](#add-whitelisted-domain-button)


#### List of whitelisted domains

The [List of whitelisted domains](#list-of-whitelisted-domains) displays all whitelisted domains. Show a [Remove whitelisted domain link](#remove-whitelisted-domain-link) for each domain.

<!-- This is to technical, find a better way to describe it -->
***Note***: *All whitelisted domains* does only refer to exception rules that match the following regexp and a member of the *SpecialSubscription* filter list:

```javascript
/^@@\|\|([^\/:]+)\^\$document$/
```

#### Remove whitelisted domain link

If clicked the corresponding whitelisted domain is removed.

*NOTE: recently added has been ommitted because we don't know the date of when a domain has been whitelisted so we could only show the domains that have been added since the option page has been opened and that doesn't make any sense?!*

### Whitelisted domain added notification

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/whitelisted-websites-notification.png'
  width='888px' />

1. [Whitelisted domain added notification](#add-whitelisted-domain-button)

#### Whitelisted domain added notification

The notification should push down page from the top and disappear if the X is
clicked or automatically after 2 seconds.

`"{}" has been added as a whitelisted website`

***TODO***: Clarification needed


Advanced tab
------------

### Advanced tab: Default

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/advanced-default.jpg' width='888px' />

1. [Advanced tab headline](#advanced-tab-headline)
1. [Advanced tab description](#advanced-tab-description)
1. [Customize section](#customize-section)
1. [Filter lists section](#filter-lists-section)
1. [Create custom filter section](#create-custom-filter-section)


#### Advanced tab: Headline

Headline for the [Advanced tab](#advanced-tab): `Advanced`

#### Advanced tab: Description

Description for the [Advanced tab](#advanced-tab): `Customize Adblock Plus, add or remove filter lists, create and maintain your own filter lists`

#### Customize section

<img src='/res/abp/options-page/advanced-default-customize.jpg' width='888px' />

1. [Customize section header](#customize-section-header)
1. [Customize: block elements](#customize-block-elements)
1. [Customize: ABP panel](#customize-adblock-plus-panel)
1. [Customize: turn off notifications](#turn-off-notifications)

#### Customize section header

`CUSTOMIZE ON-PAGE ACTIONS`

#### Customize Block Element

Checkbox to en-/disable [Block Element Context Menu Entry](#TBA).

`Show 'Block Element’ right - click menu item`

#####Tooltip: 
`Temporarily block annoying items on a webpage, e.g. images or animated slideshows.`

#### Customize Adblock Plus panel

Checkbox to en-/disable [Adblock Plus Developer Tools Panel](#TBA).

`Show 'Adblock Plus' panel in developer tools`

#####Tooltip: 
`View blocked and whitelisted items from your browser's developer tools panel.`

#### Turn off notifications

Checkbox to en-/disable [Notifications](#TBA).

`Turn off notifications`

#####Tooltip: 
`Turn off all notifications from Adblock Plus.`

#### Filter lists section

<img src='/res/abp/options-page/advanced-default-filter-lists.jpg' width='888px' />

1. [Filter list section header](#filter-list-section-header)
1. [Filter list section description](#filter-list-section-description)
1. [List of filter list subscriptions](#list-of-filter-list-subscriptions)
1. [Add filter list button](#add-filter-list-button)
1. [Update filter lists button](#update-filter-lists-button)



#### Filter list section header

`FILTER LISTS`

#### Filter list section description

```
Each Adblock Plus setting functions because of a filter list. Below are the corresponding filter lists to all your Adblock Plus settings. You can also add additional filters created and maintained by our trusted community. Learn more. [Learn more](#TBA)
```

#### List of filter list subscriptions

Status column title: `Status`

Filter List column title: `Filter lists`

Update column title: `Last updated`

List all filter list subscriptions. For each subscription show the following:

 - A *radio slider* that indicates whether or not the filter list subscription is active.
 - `Active`/`Disabled` depending on whether or not the filter list subscription is active.
 - Name of the filter list
 - Date/Time of last update
   - Show `Just now` if less then 5 minutes ago
   - Show `{} minutes ago` if more than 5 minutes ago
   - Show `{} hours ago` if the last update was within the last 24 hours
   - Show `Updating` while the list is getting updated
   - Show `Download fail` when there is a problem downloading the filter list
 - A Gear Icon that opens the [Edit filter list popup](#edit-filter-list-popup)

***TODO***: Add description of small ? sign next to Filter list column title.


#### Add filter list button

Opens [Add filter list popup](#add-filter-list-popup).

`+ Add a new filter list`

#### Update filter lists button

Updates all filters lists.

`Update all filter lists`

##### Add filter subscription popup

Allows to add a subscription.

#### Create custom filter section

<img src='/res/abp/options-page/advanced-default-custom-filter.jpg' width='888px' />

1. [Custom filter section header](#custom-filter-section-header)
1. [Custom filter section description](#custom-filter-section-description)
1. [Custom filter title](#custom-filter-title)
1. [Custom filter list placeholder](#custom-filter-list-placeholder)
1. [Create custom filter list button](#create-custom-filter-list-button)
1. [Create custom filter list link](#create-custom-filter-list-link)

#### Custom filter section header

`CREATE AND EDIT YOUR FILTER LIST`

#### Custom filter section description

`Write your own custom filters to further control what content Adblock PLus allows or blocks.`

#### Custom filter title 

`My filter list`

#### Custom filter list placeholder


`Filters you create will show up here.`

#### Create custom filter list button


`Start writing my filter list`

Opens [Advanced tab: Edit custom filter empty](#advanced-tab-edit-custom-filter-empty)

#### Create custom filter list link


[Learn how to write filter lists.](https://adblockplus.org/filters)


-------------------------------------------------------------------------------

### Advanced tab: Added filter list

<img src='/res/abp/options-page/advanced-added-filter-list.jpg' width='888px' />

Newly added filter lists should be displayed at the top and marked with a dot.

-------------------------------------------------------------------------------

### Advanced tab: Custom filter empty

<img src='/res/abp/options-page/advanced-tab-custom-filter-empty.jpg' width='888px' />

#### Advanced tab: Custom filter start button

`Start writing my filter list`

Will open [Advanced tab: Edit custom filter empty](#advanced-tab-edit-custom-filter-empty)

See also [Advanced tab: Custom filter hover](#advanced-tab-custom-filter-hover).

### Advanced tab: Custom filter hover

<img src='/res/abp/options-page/advanced-tab-custom-filter-hover.jpg' width='888px' />

[Advanced tab: Custom filter start button](#advanced-tab-custom-filter-start-button) will hover.

### Advanced tab: Edit custom filter empty

<img src='/res/abp/options-page/advanced-tab-edit-custom-filter-empty.jpg' width='888px' />

#### Advanced tab: Custom filter save button

`Save`

Will stay inactive as long as as no filter has been added.

See also [Advanced tab: Edit custom filter add](#advanced-tab-edit-custom-filter-add)

#### Advanced tab: Custom filter cancel link

`Cancel`

Will revert all changes. If no custom filter switch to [Advanced tab: Custom filter empty](#advanced-tab-custom-filter-empty) otherwise show [Advanced tab: Custom filter](#advanced-tab-custom-filter).

### Advanced tab: Edit custom filter add

<img src='/res/abp/options-page/advanced-tab-edit-custom-filter-add.jpg' width='888px' />

### Advanced tab: Custom filter

<img src='/res/abp/options-page/advanced-tab-custom-filter.jpg' width='888px' />

#### Advanced tab: Custom filter edit button

`Edit filters`

[Advanced tab: Custom filter edit button](#advanced-tab-custom-filter-edit-button) will hover.

Will open [Advanced tab: Edit custom filter edit](#advanced-tab-edit-custom-filter-edit)

###Advanced tab: Hover behavior

<img src='/res/abp/options-page/advanced-tab-edit-custom-filter-hover-2.jpg' width='888px' />

### Advanced tab: Edit custom filter edit

<img src='/res/abp/options-page/advanced-tab-edit-custom-filter-edit.jpg' width='888px' />

Edit filter list popup
----------------------

Popup to edit a filter list subscription

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/advanced-edit-filter-list-popup.jpg' width='888px' />

1. [Update filter list link](#update-filter-list-link)
1. [Filter list homepage link](#filter-list-homepage-link)
1. [Filter list source link](#filter-list-source-link)
1. [Remove filter list link](#remove-filter-list-link)

### Update filter list link

Updates this filter list.

`Update now`

### Filter list homepage link

Link to the homepage of the filter list.

`Website`

### Filter list source link

Link to the filter list file.

`Source`

### Remove filter list link

Removes the filter list subscription.
[Additional subscriptions](#additional-subscriptions) cannot be removed and the [Remove filter list link](#remove-filter-list-link) should be disabled in this case.

`Remove`



Add filter list popup
---------------------

Popup to add a filter list from a selection.

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/advanced-add-filter-list-popup.jpg' width='888px' />

1. [Add filter list popup title](#add-filter-list-popup-title)
1. [Close filter list popup X](#close-filter-list-popup-X)
1. [List of available subscriptions](#list-of-available-subscriptions)
1. [Filter list description](#filter-list-description)
1. [Scroll bar](#scroll-bar)
1. [Focused filter list](#Focussed-filter-list)
1. [Language filter list title](#language-filter-list-title)
1. [Language filter lists](#language-filter-lists)
1. [Installed filter list](#installed-filter-list)
1. [Add custom subscription link](#add-custom-subscription-link)


### Add filter list popup title

`Add filter subscription`

### Close filter list popup X

Closes the [Add filter list popup](#add-filter-list-popup).

### List of available subscriptions

- Subscription title `EasyPrivacy`
 - Description `Block tracking`
 - URL: https://easylist-downloads.adblockplus.org/easyprivacy.txt
- Subscription title `Malware Domains`
 - Description `Block malware`
 - URL: https://easylist-downloads.adblockplus.org/malwaredomains_full.txt
- Subscription title `Adblock Warning Removal List`
 - Description `Removes anti-adblock warnings and other obtrusive messagesl`
 - URL: https://easylist-downloads.adblockplus.org/antiadblockfilters.txt
- Subscription title `Adware filters`
 - Description `Blocks ads injected by adware`
 - URL: https://easylist-downloads.adblockplus.org/adwarefilters.txt
- Subscription title `Fanboy's Annoyances`
 - Description `Removes online annoyances (includes Fanboy's Social Blocking List).`
 - URL: https://easylist-downloads.adblockplus.org/fanboy-annoyance.txt
- Subscription title `Fanboy's Social Blocking List`
 - Description `Removes social media integration.`
 - URL: https://easylist-downloads.adblockplus.org/fanboy-social.txt
- Subscription title `I don't care about cookies`
 - Description `Filters obtrusive EU cookie law notices.`
 - URL: https://kiboke-studio.hr/i-dont-care-about-cookies/abp
- Subscription title `Spam404`
 - Description `Block fraudulent websites.`
 - URL: https://raw.githubusercontent.com/Dawsey21/Lists/master/adblock-list.txt
- Subscription title `CJX's Annoyance List`
 - Description `Removes self-promotion and privacy protection for EasyList China`
 - URL: https://raw.githubusercontent.com/cjx82630/cjxlist/master/cjx-annoyance.txt

Filter list subscriptions here: https://adblockplus.org/subscriptions

### Filter list descriptions

See above for filter list subscriptions and corresponding descriptions. 

### Scroll bar

The size of the layover menu should correspond to the screen size. The scroll bar should adjust accordingly. 

### Focused filter list

When a filter list is focused on the whole row should be highlighted.

### Language filter list title

`Languages`

All language filter lists will be grouped separately beneath the title.

### Language filter lists

- Subscription title `EasyList`
 - Description `English`
 - URL: https://easylist-downloads.adblockplus.org/easylist.txt
- Subscription title `ABPindo`
 - Description `Bahasa Indonesia`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/abpindo+easylist.txt
 - URL alone: https://raw.githubusercontent.com/ABPindo/indonesianadblockrules/master/subscriptions/abpindo.txt
- Subscription title `Bulgarian list`
 - Description `български`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/bulgarian_list+easylist.txt
 - URL alone: https://stanev.org/abp/adblock_bg.txt
- Subscription title `EasyList China`
 - Description `中文`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/easylistchina+easylist.txt
 - URL alone: https://easylist-downloads.adblockplus.org/easylistchina.txt
- Subscription title `EasyList Czech and Slovak`
 - Description `čeština, slovenčina`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/easylistczechslovak+easylist.txt
 - URL alone: https://raw.github.com/tomasko126/easylistczechandslovak/master/filters.txt
- Subscription title `EasyList Dutch`
 - Description `Nederlands`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/easylistdutch+easylist.txt
 - URL alone: https://easylist-downloads.adblockplus.org/easylistdutch.txt
- Subscription title `EasyList Germany`
 - Description `Deutsch`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/easylistgermany+easylist.txt
 - URL alone: https://easylist-downloads.adblockplus.org/easylistgermany.txt
- Subscription title `EasyList Hebrew`
 - Description `עברית`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/israellist+easylist.txt
 - URL alone: https://raw.githubusercontent.com/easylist/EasyListHebrew/master/EasyListHebrew.txt
- Subscription title `EasyList Italy`
 - Description `Italiano`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/easylistitaly+easylist.txt
 - URL alone: https://easylist-downloads.adblockplus.org/easylistitaly.txt
- Subscription title `EasyList Lithuania`
 - Description `lietuvių kalba`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/easylistlithuania+easylist.txt
- Subscription title `EasyList Latvian`
 - Description `latviešu valoda`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/latvianlist+easylist.txt
 - URL alone: https://notabug.org/latvian-list/adblock-latvian/raw/master/lists/latvian-list.txt
- Subscription title `EasyList Spanish`
 - Description `Español`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/easylistspanish+easylist.txt
 - URL alone: https://easylist-downloads.adblockplus.org/easylistspanish.txt
- Subscription title `EasyList AR`
 - Description `العربية`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/liste_ar+liste_fr+easylist.txt
 - URL alone: https://easylist-downloads.adblockplus.org/Liste_AR.txt
- Subscription title `EasyList FR`
 - Description `Français`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/liste_fr+easylist.txt
 - URL alone: https://easylist-downloads.adblockplus.org/liste_fr.txt
- Subscription title `ROList`
 - Description `Românesc`
 - URL + EasyList: https://easylist-downloads.adblockplus.org/rolist+easylist.txt
 - URL alone: https://easylist-downloads.adblockplus.org/advblock.txt
- Subscription title `Icelandic ABP List`
 - Description `íslenska`
 - URL + EasyList: https://adblock.gardar.net/is.abp.txt
- Subscription title `void.gr`
 - Description `ελληνικά`
 - URL + EasyList: https://void.gr/kargig/void-gr-filters.txt
- Subscription title `ABP Japanese Filters`
 - Description `日本語`
 - URL: https://raw.githubusercontent.com/k2jp/abp-japanese-filters/master/abpjf.txt
- Subscription title `ABPVN List`
 - Description `Việt`
 - URL: https://raw.githubusercontent.com/abpvn/abpvn/master/filter/abpvn.txt
- Subscription title `Adblock List for Finland`
 - Description `suomi`
 - URL: http://adb.juvander.net/Finland_adb.txt
- Subscription title `Czech List`
 - Description `čeština`
 - URL: http://adblock.dajbych.net/adblock.txt
- Subscription title `Eesti saitidele kohandatud filter`
 - Description `Eesti keel`
 - URL: http://adblock.ee/list.php
- Subscription title `hufilter`
 - Description `magyar`
 - URL: https://raw.githubusercontent.com/szpeter80/hufilter/master/hufilter.txt
- Subscription title `YousList`
 - Description `한국어`
 - URL: https://raw.githubusercontent.com/yous/YousList/master/youslist.txt

  
### Installed filter list

Installed filter lists will appear in the menu, but should be disabled.

### Add custom subscription link

Closes the [Add filter list popup](#add-filter-list-popup) and opens the [Add custom subscription popup](#add-custom-subscription-popup)

`+ Add a filter list via URL`


Add custom subscription popup
-----------------------------

### Add custom subscription popup: Initial
<!-- XXX: don't use html -->
<img src='/res/abp/options-page/add-custom-subscription-popup.jpg' width='888px' />

1. [Custom subscription popup title](#custom-subscription-popup-title)
1. [Close custom subscription popup X](#close-custom-subscription-popup-X)
1. [Custom subscription popup subscription title input](#custom-subscription-popup-subscription-title-input)
1. [Custom subscription popup subscription url input](#custom-subscription-popup-subscription-url-input)
1. [Custom subscription popup cancel button](#custom-subscription-popup-cancel-button)
1. [Custom subscription popup add button](#custom-subscription-popup-add-button)


#### Custom subscription popup title

`Add a filter list`

#### Custom subscription popup X

Closes the [Add custom subscription popup](#add-custom-subscription-popup)

#### Custom subscription popup subscription title input

Label `Subscription title:`

Placeholder `Filter subscription title`

Auto focus when [Add custom subscription popup](#add-custom-subscription-popup) is opened.

Validate as you type: Not Empty.

#### Custom subscription popup subscription url input

Label `Filter list location`.

Placeholder `https://website.com/filterlist.txt`

Validates as you type against:

<!-- This is to technical, find a better way to describe it -->
```javascript
/^https?:/i
```


### Add custom subscription popup: Invalid
<!-- XXX: don't use html -->
<img src='/res/abp/options-page/add-custom-subscription-popup-invalid.jpg' width='888px' />

If [Custom subscription popup subscription url input](#Custom-subscription-popup-subscription-url-input) is invalid show a small red *!*.

### Add custom subscription popup: Valid
<!-- XXX: don't use html -->
<img src='/res/abp/options-page/add-custom-subscription-popup-valid.jpg' width='888px' />

If [Custom subscription popup subscription url input](#Custom-subscription-popup-subscription-url-input) is valid show a green *✓*.

#### Custom subscription popup cancel button

Closes the [Add custom subscription popup](#add-custom-subscription-popup)

`Cancel`

#### Custom subscription popup add button

Inactive as long as [Custom subscription popup subscription title input](#custom-subscription-popup-subscription-title-input) and [Custom subscription popup subscription url input](#Custom-subscription-popup-subscription-url-input) don't validate.

Adds filter list.

See [Advanced tab added filter list](#advanced-tab-added-filter-list)

`Add filter list`

Additional subscriptions
------------------------

[Additional subscriptions](#additional-subscriptions) are subscriptions that are added through group policies and cannot be removed See <https://issues.adblockplus.org/ticket/3801>
