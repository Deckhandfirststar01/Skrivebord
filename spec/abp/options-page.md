Options Page
============

Options page for the ABP Browser extension.

The options page is used to change various options of the ABP browser extension.
<a name="top"></a>

1. [Navigation menu](#markdown-navigation-menu)
1. [About ](#markdown-About)
1. [General tab](#markdown-header-general-tab)
1. [Whitelist tab](#markdown-header-whitelist-tab)
1. [Advanced tab](#markdown-header-advanced-tab)
1. [Help tab](#markdown-header-help-tab)
1. [Assets](#markdown-header-assets)

## General requirements

### Bidirectionailty

Any change of state will be immediately reflected in the options page regardless
of where and how the change was made, so that the options page always reflects
the current state of the extension.

- If the user opens the option page more than once and makes changes to either of them, the change will be reflected in any of them and not just the one the change was made. 
- If a change to the state was made through other means e.g. auto update of filter list subscriptions, it will be reflected immediately in every instance of the options page.

### Style Guide

All UI patterns are defined in the [Options page Style Guide](/res/abp/options-page/options_page_style_guide.pdf).

### WCAG

Should implement the following [WCAG 2.0 Guidelines](http://www.w3.org/TR/2008/REC-WCAG20-20081211/):

- 2.1 Keyboard Accessible
- 2.4 Navigable

## Navigation

Implement <https://www.w3.org/TR/2016/WD-wai-aria-practices-1.1-20161214/#tabpanel>

Navigation menu
-------------

### Navigation menu default

![](/res/abp/options-page/navigation-menu.jpg)

1. [Logo](#markdown-logo)
1. [Navigation menu list](#markdown-navigation-menu-list)
1. [Contribute button](#markdown-contribute-button)
1. [About link](#markdown-about-link)

#### Logo
- This will appear consistently across all tabs.
- All elements within the navigation menu are fixed according to the screen height.
- `Adblock Plus Settings`

#### Navigation menu list

Navigation names should match the headlines of each tab.
1. [General tab headline](#markdown-general-tab-headline)
1. [Whitelisted tab headline](#markdown-whitelisted-tab-headline)
1. [Advanced tab headline](#markdown-advanced-tab-headline)
1. [Help tab headline](#markdown-help-tab-headline)

#### Contribute button
Opens the [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link): `%LINK%=contribute` in a new tab

#### About link
Opens the [About](#markdown-about) overlay.

### About

![](/res/abp/options-page/navigation-about.jpg)

- Title: `About Adblock Plus`
- Version number of extension added dynamically: `Version number xxx`
- Text: `Copyright © 2016 eyeo GmbH.
Adblock Plus is a registered ® trademark of eyeo GmbH.`
- Button to close layover: `Close` 
- X closes the layover.

General tab
-------------
### General tab default

![](/res/abp/options-page/general-tab.jpg)

1. [General tab headline](#markdown-header-general-tab-headline)
1. [General tab description](#markdown-header-general-tab-description)
1. [Privacy & Security section](#markdown-header-privacy--security-section)
1. [Acceptable Ads section](#markdown-header-acceptable-ads-section)
1. [Language section](#markdown-header-language-section)
1. [More filters section](#markdown-header-more-filters-section)

#### General tab headline

- Headline for the [General tab](#markdown-header-general-tab) `General`
- Navigation label will match headline.

#### General tab description

Description for the [General tab](#markdown-header-general-tab).

```
Determine what Adblock Plus shows and hides on websites
```

### Privacy & Security section

![](/res/abp/options-page/general-default-privacy-and-security.jpg)

1. [Privacy section headline](#markdown-header-privacy-tab-headline)
1. [Recommended filter lists](#markdown-header-recommended-filter-lists)
1. [Tooltip icon](#markdown-header-tooltip-icon)
1. [Tooltip pop-up](#markdown-header-tooltip-pop-up)

#### Privacy & Security section headline

Headline for the [Privacy & security section](#markdown-header-privacy-&-security-section) `PRIVACY & SECURITY`

#### Recommended filter lists

Checkbox to install/uninstall each filter list.

| Filter list name | Filter list title | Tooltip | Filter list URL |
|-----------|---------------|---------------|--------------|
| Fanboy's Annoyances | `Block social media tracking` | `The social media buttons (or icons) on the websites that you visit allow social media networks to build a profile of you based on your browsing habits - even when you don’t click on them. Hiding these buttons can protect your profile.` | https://easylist-downloads.adblockplus.org/fanboy-annoyance.txt |
| EasyPrivacy | `Disable tracking` | `Protect your personal data by removing all forms of tracking from the Internet including information collectors.` | https://easylist-downloads.adblockplus.org/easyprivacy.txt |

#### Tooltip icon

- Tooltip is triggered when a users clicks on the icon. 

#### Tooltip pop-up

Refer to the table in [Recommended filter lists](#markdown-header-recommended-filter-lists)
 for tooltip descriptions. 

### Acceptable Ads section

![](/res/abp/options-page/general-default-acceptable-ads.jpg)

1. [Acceptable Ads section headline](#markdown-header-acceptable-ads-section-headline)
1. [Acceptable Ads section description](#markdown-header-acceptable-ads-section-description)
1. [Acceptable Ads table](#markdown-header-acceptable-ads-table)
1. [Acceptable Ads notification](#markdown-header-acceptable-ads-notification)

#### Acceptable Ads section headline

- Headline for the [Acceptable Ads section](#markdown-header-acceptable-ads-section) `ACCEPTABLE ADS`

#### Acceptable Ads section description

Description for the [Acceptable Ads section](#markdown-header-acceptable-ads-section) 

```Acceptable Ads are nonintrusive ads. They are the middle ground between ad blocking and supporting online content because they generate revenue for website owners.```

#### Acceptable Ads table

- Radio button options.
- `Show nonintrusive ads` is selected on default. This enables the `Allow nonintrusive advertising` (URL: https://easylist-downloads.adblockplus.org/exceptionrules.txt) filter list.

| Title | Description | Action |
|-----------|---------------|--------------|
| `Allow some nonintrusive ads` | `Nonintrusive ads are not annoying and do not interfere with the content you are viewing. These ads collect some information about your browsing habits to provide you with more relevant ads.  [Read more about the nonintrusive ad criteria][1]` `**Note:** The ads collect data about your browsing habits **_not_** Adblock Plus.` | Enables `Allow non-intrusive advertising` filter list. |
| `Allow only nonintrusive ads that are privacy-friendly` | `These ads do not collect personal user information and, therefore, may be less relevant.` | Enables Privacy friendly ads |
| `Block all ads` | N/A | Disables `Allow nonintrusive advertising` filter list. |

[1]: Opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link): `%LINK%=acceptable_ads_criteria` in a new tab.

##### Show nonintrusive ads

The default setting.

##### Show nonintrusive ads that are privacy friendly

- This is a subset of the `Nonintrusive ads` which complies with [EEF’s DNT policy](https://www.eff.org/pages/understanding-effs-do-not-track-policy-universal-opt-out-tracking). 
- Label this setting as `NEW` during the user's first visit to the new options page. 
- If a user selects this option AND has DNT disabled, display the below text within the table:

```**Note:** You have **Do Not Track (DNT)** disabled in your Chrome settings. For this feature to work properly, please enable **DNT** in your browser preferences. [Find out how to enable DNT][1] and redirect to the official browser instructions for enabling DNT)```

[1]: Opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link): `%LINK%=(adblock_plus_chrome_dnt|adblock_plus_firefox_dnt|adblock_plus_opera_dnt|adblock_plus_edge_dnt)` depending on which browser the extension is running in a new tab.

![](/res/abp/options-page/general-default-acceptable-ads-dnt.jpg)

#### Acceptable Ads notification

- If a user enables `Disable tracking` (EasyPrivacy) and `Show nonintrusive ads` (Acceptable Ads), then show the below notification. This is a one time message. 

![](/res/abp/options-page/general-acceptable-ads-notification.jpg)

- Notifcation title: `Allow tracking on Acceptable Ads?`

- Notifcation text:
```
You currently allow Acceptable Ads to be shown.
These ads are respectful and do not interfere with content that you view.
Some of these ads require tracking to show you more relevant ads.
Click *YES* to continue seeing relevant nonintrusive ads.
```
- Buttons

| Button label | Behaviour | 
|-----------|---------------|
| `YES, ALLOW RELEVANT ADS` | Keeps selection on `Show nonintrusive ads`, and closes window |
| `NO, TURN OFF TRACKING` | Switches selection to `Show nonintrusive ads that are privacy-friendly`, and closes window |

```
Note:
* Ability to disable tracking depends on completeness of the EasyPrivacy filter list.
* Adblock Plus does not directly show ads.
* Adblock Plus never tracks any information.
```

### Language section

![](/res/abp/options-page/general-default-language.jpg)

1. [Language section headline](#markdown-header-language-section-headline)
1. [Language section description](#markdown-header-language-section-description)
1. [Default language](#markdown-header-default-language)
1. [Change language](#markdown-header-change-language)
1. [Add language](#markdown-header-add-language)
1. [Language tip](#markdown-header-language-tip)

#### Language section headline

- Headline for the [Language section](#markdown-header-language-section) `Language`

#### Language section description

Description for the [Language section](#markdown-header-language-section) 

```Optimize Adblock Plus for the language(s) you typically browse websites in. [Learn more](#markdown-header-link to Help Centre article (needs to be created still)```

TODO link to language article

#### Default language

- Language filter list selected based on the browser's default language.
- To see all available language options and corresponding filter lists go to  [Language filter lists](#markdown-header-language-filter-lists).

#### Change language

- Labelled `CHANGE`
- Button to trigger the [language drop-down menu](#markdown-header-language-drop-down-menu).

#### Add language

- Labelled `+ ADD A LANGUAGE` 
- Button to trigger the [language drop-down menu](#markdown-header-language-drop-down-menu).

#### Language tip

```**TIP:** Only select the languages you need. Selecting more will slow down the ad blocker and, therefore, your browsing speed. ```

#### Adding / Changing a language

![](/res/abp/options-page/general-default-language-drop-down.jpg)

1. [Language list](#markdown-header-language-list)
1. [Dropdown header](#markdown-header-dropdown-header)
1. [Selecting a language](#markdown-header-selecting-a-language)
1. [Selected language](#markdown-header-selected-language)

#### Language list

- To see all available language options and corresponding filter lists go to  [Language filter lists](#markdown-header-language-filter-lists).

#### Dropdown header

- Labelled `Select a language` 

#### Selecting a language

- Hover over and click states are displayed in the same way. 
- `CHANGE` state: Triggers language drop down. Clicking on a language will automatcically close the drop down menu and *add the language the list*. 
- `+ ADD A LANGUAGE` state: Triggers language drop down. Clicking on a language will automatcically close the drop down menu and *change the default language*. 

#### Selected language

- Selected language(s) are greyed out and not interactive. 
- When a user is  changing their default language using the [change language](#markdown-header-change-language) feature, there will be no `selected language` state.
- If another language has already been added as a secondary language, a user will be able to select that language. This will change the language to the default language, and move it to the top of the language list.   

#### Removing a language

![](/res/abp/options-page/general-default-language-multiple.jpg)

- When there is more than 1 language filter list in the table, the `CHANGE` element turns into a bin icon. All filter lists are removeable.
- To remove a language from the table, select the bin icon in the language row. 
- When there is only 1 language filter list in the table, the remaining filter list is not removeable, and the user is only allowed to `CHANGE` the filter list - this triggers the language drop down.

#### Language filter list - empty state

![](/res/abp/options-page/general-tab-language-empty.jpg)

- When alll language filter lists have been removed from the extension.
- Text: `You don't have any language specific filters.`
- Note: it is only possible to remove all language filter lists in [Remove filter list subscriptions](#markdown-header-remove-filter-list-subscriptions) in the Advanced tab.

### More filters section

![](/res/abp/options-page/general-default-more-filters.jpg)

1. [More filters section headline](#markdown-header-language-section-headline)
1. [More filters section description](#markdown-header-language-section-description)
1. [More filter subscriptions](#markdown-header-more-filter-subscriptions)
1. [More filters tooltip](#markdown-header-more-filters-tooltip)
1. [Remove more filters](#markdown-header-remove-more-filters)
1. [More filters note](#markdown-header-more-filters-note)

#### More filters section headline

Headline for the [More filters section](#markdown-header-more-filters-section) `More filters`

#### Language section description

Description for the [More filters section](#markdown-header-more-filters-section) 

```These are additional filters you previously added to Adblock Plus.```

#### More filter subscriptions

All filter lists that a user subscribes to which are not one of Adblock Plus's recommended filter lists (i.e. not recommended within the `Privacy & Security` and `Language` sections) will be shown here. 

#### More filters tooltips

If no description is available, the tooltip icon is hidden.

| Filter list name | Tooltip description | 
|-----------|---------------|
| Adware filters | `Adware is software that is typically obtained without your consent. It displays unwanted ads when you are online and can also track your browsing habits.` |
| Malware Domains | `Malicious software (or "malware") is software that is intended to gain access to and damage your computer. Computer viruses, worms, spyware and Trojan horses are all forms of malware.` |
| Spam404 | `Fraudulent websites, or scam websites, may look legit but are filled with adware, malware, spam or other harmful elements.` |
| Adblock Warning Removal List | `Some websites show messages that ask you to turn off your ad blocker. Access to content will not be limited on sites that require no action from you (i.e. you are not required to turn off Adblock Plus to access the content).` |

#### Remove more filters

You can only remove filters from the panel here, by clicking on the `Remove` button.

#### More filters notes

Description `**Note:** These filters are managed by third party authors. Adblock Plus is not responsible for them.`

Whitelist tab
-------------
[Back to top of page](#markdown-header-options-page)

### Whitelist tab empty

![](/res/abp/options-page/whitelisted-websites.jpg)

1. [Whitelist tab headline](#markdown-header-whitelist-tab-headline)
1. [Whitelist tab description](#markdown-header-whitelist-tab-description)
1. [Whitelist textinput](#markdown-header-whitelist-textinput)
1. [Add whitelisted domain button](#markdown-header-add-whitelisted-domain-button)
1. [Add whitelisted domain error message](#markdown-header-add-whitelisted-domain-error-message)
1. [Empty Whitelist placeholder](#markdown-header-empty-whitelist-placeholder)

#### Whitelist tab headline

- Headline for the [Whitelist tab](#markdown-header-whitelist-tab) `Whitelisted websites`
- Navigation label will match headline.

#### Whitelist tab description

Description for the [Whitelist tab](#markdown-header-whitelist-tab).

```
You’ve turned off ad blocking on these websites and, therefore, will see ads on them. [Learn more][1]
```
[1]: [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) *whitelist*

#### Whitelist textinput

- Textinput to enter domains to be added to the whitelist.
- Instruction label in text input `e.g. www.example.com`
- When a duplicate entry is made, move the original entry to the top of the list and discard the duplicate.

#### Add whitelisted domain button

 - Button to submit [Whitelist textinput](#markdown-header-whitelist-textinput).
 - Labelled `Add website`
 - Refer to [w3 guidelines for keyboard interaction](https://www.w3.org/TR/2016/WD-wai-aria-practices-1.1-20161214/#button)
 - If clicked whitelist domain and show [Whitelisted domain added notification](#markdown-header-whitelisted-domain-added-notification).

> A whitelisted domain is an exception rule filter for a certain host.

#### Add whitelisted domain error message

Shows an error message if [Add whitelisted domain textinput](#markdown-header-add-whitelisted-domain-textinput) doesn't validate.

See [Add whitelisted domain textinput](#markdown-header-add-whitelisted-domain-textinput) for more details.

#### Empty Whitelist placeholder

Placeholder text shown as long as there are no whitelisted domains.

 - `You don't have any whitelisted websites.`
 - `Websites you trust and want to allow ads on will be shown here.`

### Whitelist tab populated

![](/res/abp/options-page/whitelisted-websites-populated.jpg)

1. [List of whitelisted domains](#markdown-header-add-whitelisted-domain-button)

#### List of whitelisted domains

- Displays all whitelisted domains. 
- Show a [Remove whitelisted domain link](#markdown-header-remove-whitelisted-domain-link) for each domain.
- List items are sorted alphabetically when loaded.
- Move newly added items (from the current session) to the top of the list.
- When a duplicate domain entry is made, move the original entry to the top of the list.

<!-- This is to technical, find a better way to describe it -->
***Note***: *All whitelisted domains* does only refer to exception rules that match the following regexp and a member of the *SpecialSubscription* filter list:

```javascript
/^@@\|\|([^\/:]+)\^\$document$/
```

#### Remove whitelisted domain link

When clicked the corresponding whitelisted domain is removed.

*NOTE: recently added has been ommitted because we don't know the date of when a domain has been whitelisted so we could only show the domains that have been added since the option page has been opened and that doesn't make any sense?!*

### Whitelisted domain added notification

![](/res/abp/options-page/whitelisted-websites-notification.jpg)

1. [Whitelisted domain added notification](#markdown-header-add-whitelisted-domain-button)

#### Whitelisted domain added notification

- The notification should appear as an overlay sliding in from the top of the page.
- The notification will disappear if the X is clicked or automatically after 3 seconds.
- `"<website>" has been whitelisted.`

Advanced tab
------------
[Back to top of page](#markdown-header-options-page)

### Advanced tab: Default

![](/res/abp/options-page/advanced-default.jpg)

1. [Advanced tab headline](#markdown-header-advanced-tab-headline)
1. [Advanced tab description](#markdown-header-advanced-tab-description)
1. [Customize section](#markdown-header-customize-section)
1. [Filter lists section](#markdown-header-filter-lists-section)
1. [Create custom filter section](#markdown-header-create-custom-filter-section)


#### Advanced tab: Headline

- Headline for the [Advanced tab](#markdown-header-advanced-tab): `Advanced`
- Navigation label will match headline.


#### Advanced tab: Description

Description for the [Advanced tab](#markdown-header-advanced-tab): `Customize Adblock Plus, add or remove filter lists, create and maintain your own filter lists`

#### Customize section

![](/res/abp/options-page/advanced-default-customize.jpg)

1. [Customize section header](#markdown-header-customize-section-header)
1. [Customize: block elements](#markdown-header-customize-block-elements)
1. [Customize: ABP panel](#markdown-header-customize-adblock-plus-panel)
1. [Customize: turn off notifications](#markdown-header-turn-off-notifications)

#### Customize section header

`CUSTOMIZE ON-PAGE ACTIONS`

#### Customize Block Element

- Checkbox to en-/disable [Block Element Context Menu Entry](#markdown-header-TBA).
- `Show 'Block Element’ right-click menu item`

##### Tooltip:
 
- `Temporarily block annoying items on a webpage, e.g. images or animated slideshows.`
- Behaviour specified in [Tooltip icon](#markdown-header-tooltip-icon).

#### Customize Adblock Plus panel

- Checkbox to en-/disable [Adblock Plus Developer Tools Panel](#markdown-header-TBA).
- `Show 'Adblock Plus' panel in developer tools`

##### Tooltip: 
- `View blocked and whitelisted items from your browser's developer tools panel.`
- Behaviour specified in [Tooltip icon](#markdown-header-tooltip-icon).

#### Turn off notifications

- Checkbox to en-/disable [Notifications](#markdown-header-TBA).
- `Turn off notifications`

##### Tooltip: 
- `Turn off all notifications from Adblock Plus.`
- Behaviour specified in [Tooltip icon](#markdown-header-tooltip-icon).

#### Filter lists section

- Filter list subscriptions are displayed in a grid format. Keyboard interations should follow guidelines as specified by [w3 data: Grids for presenting tabular information](https://www.w3.org/TR/2016/WD-wai-aria-practices-1.1-20161214/#dataGrid)

![](/res/abp/options-page/advanced-default-filter-lists.jpg)

1. [Filter list section header](#markdown-header-filter-list-section-header)
1. [Filter list section description](#markdown-header-filter-list-section-description)
1. [Filter list subscriptions status](#markdown-header-filter-list-subscriptions-status)
1. [Filter list title](#markdown-header-filter-list-title)
1. [Filter list subscriptions updates](#markdown-header-filter-list-subscriptions-updates)
1. [Filter list subscriptions settings](#markdown-header-filter-list-subscriptions-settings)
1. [Remove filter list subscriptions](#markdown-header-remove-filter-list-subscriptions)
1. [Add filter list button](#markdown-header-add-filter-list-button)
1. [Update filter lists button](#markdown-header-update-filter-lists-button)

#### Filter list section header

`FILTER LISTS`

#### Filter list section description

`Each Adblock Plus setting functions because of a filter list. Below are the filter lists that correspond to all of your Adblock Plus
settings. You can also add additional filters created and maintained by our trusted community. [Learn more][1]`
[1]: [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) *subscriptions*

#### Filter list subscriptions status

- Column title: `Status`
- *Radio slider*  indicates whether or not the filter list subscription is active.
- `Active`/`Disabled` depending on whether or not the filter list subscription is active.
- Exception: Acceptable Ads filter list can only be deleted and added, this filter list can not be disabled (the filter list toggle is inactive as a result).

#### Filter list title

- Column title: `Filter lists`
- Displays name of the filter list
- Lists are sorted alphabetically when loaded.
- Move newly added items (from the current session) to the top of the list.

#### Filter list subscriptions updates

 - Column title: `Last updated`
 - Date/Time of last filter list update
     - Show `Just now` if less then 5 minutes ago
     - Show `{} minutes ago` if more than 5 minutes ago
     - Show `{} hours ago` if the last update was within the last 24 hours
     - Show `DD MMM YYYY` (eg. 10 Jul 2017) if the update was more than 24 hours ago
     - Show `Updating` while the list is getting updated
     - Show `Download fail` when there is a problem downloading the filter list
     - All date and time status for filter lists should be updated as filter lists are updated.

#### Filter list subscriptions settings

 - A Gear Icon opens the [Edit filter list popup](#markdown-header-edit-filter-list-popup)

#### Remove filter list subscriptions

- trash.svg icon deletes the filter list. 

#### Add filter list button

- Opens [Add filter list popup](#markdown-header-add-filter-list-popup).
- `+ Add a new filter list`

#### Update filter lists button

- `Update all filter lists`
- Click to button will update all dates and time status for filter lists.

Edit filter list popup
----------------------

- Popup to edit a filter list subscription.
- The popup menu should follow [arai best practices](https://www.w3.org/TR/2016/WD-wai-aria-practices-1.1-20161214/#menu) for keyboard interactions.  
- Clicking outside closes the menu if the menu is open.
- Clicking on a menu item closes the menu.

![](/res/abp/options-page/advanced-edit-filter-list-popup.jpg)

1. [Update filter list link](#markdown-header-update-filter-list-link)
1. [Filter list homepage link](#markdown-header-filter-list-homepage-link)
1. [Filter list source link](#markdown-header-filter-list-source-link)
1. [Remove filter list link](#markdown-header-remove-filter-list-link)

### Update filter list link

- Updates this filter list.
- `Update now`

### Filter list homepage link

- Link to the homepage of the filter list.
- `Website`

### Filter list source link

- Link to the filter list file.
- `Source`

### Remove filter list link

- Removes the filter list subscription.
[Additional subscriptions](/spec/abp/prefs.md#markdown-header-additional-subscriptions) cannot be removed and the [Remove filter list link](#markdown-header-remove-filter-list-link) should be disabled in this case.
- `Remove`

Add filter list popup
---------------------

Popup to add a filter list from a selection.

![](/res/abp/options-page/advanced-add-filter-list-popup.jpg)

1. [Add filter list popup title](#markdown-header-add-filter-list-popup-title)
1. [Close filter list popup X](#markdown-header-close-filter-list-popup-X)
1. [Filter subscription](#markdown-header-filter-subscription)
1. [Scroll bar](#markdown-header-scroll-bar)
1. [Focused filter list](#markdown-header-Focussed-filter-list)
1. [Add filter list via URL](#markdown-header-add-filter-list-via-URL)

### Add filter list popup title

`Add filter subscription`

### Close filter list popup X

Closes the [Add filter list popup](#markdown-header-add-filter-list-popup).

### Filter subscription

- Show filter *Subscription title* in the first column and filter *Description* in the second column. See [Language filter lists](#markdown-header-language-filter-lists) for titles and description.
- Already added filter subscriptions will appear disabled in the popup. 

### Scroll bar

The size of the layover menu should correspond to the screen size. The scroll bar should adjust accordingly. 

### Focused filter list

When a filter list is in focus the whole row should be highlighted.

### Add filter list via URL

- Closes the [Add filter list popup](#markdown-header-add-filter-list-popup) and opens the [Add custom subscription popup](#markdown-header-add-custom-subscription-popup)
- `+ ADD FILTER LIST VIA URL`

### Language filter lists

| Subscription title | Description | URL + EasyList | URL | 
|-----------|---------------|---------------|---------------|
| `EasyList` | `English` | https://easylist-downloads.adblockplus.org/easylist.txt | |
| `ABPindo` | `Bahasa Indonesia` | https://easylist-downloads.adblockplus.org/abpindo+easylist.txt | https://raw.githubusercontent.com/ABPindo/indonesianadblockrules/master/subscriptions/abpindo.txt |
| `Bulgarian list` | `български` | https://easylist-downloads.adblockplus.org/bulgarian_list+easylist.txt | https://stanev.org/abp/adblock_bg.txt |
| `EasyList China` | `中文` | https://easylist-downloads.adblockplus.org/easylistchina+easylist.txt | https://easylist-downloads.adblockplus.org/easylistchina.txt |
| `EasyList Czech and Slovak` | `čeština, slovenčina` | https://easylist-downloads.adblockplus.org/easylistczechslovak+easylist.txt | https://raw.github.com/tomasko126/easylistczechandslovak/master/filters.txt |
| `EasyList Dutch` | `Nederlands` | https://easylist-downloads.adblockplus.org/easylistdutch+easylist.txt | https://easylist-downloads.adblockplus.org/easylistdutch.txt |
| `EasyList Germany` | `Deutsch` | https://easylist-downloads.adblockplus.org/easylistgermany+easylist.txt | https://easylist-downloads.adblockplus.org/easylistgermany.txt |
| `EasyList Hebrew` | `עברית` | https://easylist-downloads.adblockplus.org/israellist+easylist.txt | https://raw.githubusercontent.com/easylist/EasyListHebrew/master/EasyListHebrew.txt |
| `EasyList Italy` | `Italiano` | https://easylist-downloads.adblockplus.org/easylistitaly+easylist.txt | |
| `EasyList Lithuania` | `lietuvių kalba` | https://easylist-downloads.adblockplus.org/easylistlithuania+easylist.txt | |
| `EasyList Latvian` | `latviešu valoda` | https://easylist-downloads.adblockplus.org/latvianlist+easylist.txt | https://notabug.org/latvian-list/adblock-latvian/raw/master/lists/latvian-list.txt |
| `EasyList Spanish` | `Español` | https://easylist-downloads.adblockplus.org/easylistspanish+easylist.txt | https://easylist-downloads.adblockplus.org/easylistspanish.txt |
| `EasyList AR` | `العربية` | https://easylist-downloads.adblockplus.org/liste_ar+liste_fr+easylist.txt | https://easylist-downloads.adblockplus.org/Liste_AR.txt |
| `EasyList FR` | `Français` | https://easylist-downloads.adblockplus.org/liste_fr+easylist.txt | https://easylist-downloads.adblockplus.org/liste_fr.txt |
| `ROList` | `Românesc` | https://easylist-downloads.adblockplus.org/rolist+easylist.txt | https://easylist-downloads.adblockplus.org/advblock.txt |
| `Icelandic ABP List` | `íslenska` | https://adblock.gardar.net/is.abp.txt | |
| `void.gr` | `ελληνικά` | https://void.gr/kargig/void-gr-filters.txt | |
| `ABP Japanese Filters` | `日本語` | https://raw.githubusercontent.com/k2jp/abp-japanese-filters/master/abpjf.txt | |
| `ABPVN List` | `Việt` | https://raw.githubusercontent.com/abpvn/abpvn/master/filter/abpvn.txt | |
| `Adblock List for Finland` | `suomi` | http://adb.juvander.net/Finland_adb.txt | |
| `Czech List` | `čeština` | http://adblock.dajbych.net/adblock.txt | |
| `Eesti saitidele kohandatud filter` | `Eesti keel` |  http://adblock.ee/list.php | |
| `hufilter` | `magyar` | https://raw.githubusercontent.com/szpeter80/hufilter/master/hufilter.txt | |
| `YousList` | `한국어` | https://raw.githubusercontent.com/yous/YousList/master/youslist.txt | |

Add custom subscription popup
-----------------------------

### Add custom subscription popup: Initial
![](/res/abp/options-page/add-custom-subscription-popup.jpg)

1. [Custom subscription popup title](#markdown-header-custom-subscription-popup-title)
1. [Close custom subscription popup X](#markdown-header-close-custom-subscription-popup-X)
1. [Custom subscription popup subscription title input](#markdown-header-custom-subscription-popup-subscription-title-input)
1. [Custom subscription popup subscription url input](#markdown-header-custom-subscription-popup-subscription-url-input)
1. [Custom subscription popup cancel button](#markdown-header-custom-subscription-popup-cancel-button)
1. [Custom subscription popup add button](#markdown-header-custom-subscription-popup-add-button)


#### Custom subscription popup title

`Add a filter list`

#### Custom subscription popup X

Closes the [Add custom subscription popup](#markdown-header-add-custom-subscription-popup)

#### Custom subscription popup subscription title input

- Label `Filter list name`
- When the text field is active or contains data, the label floats above the input area.
- Auto focus when [Add custom subscription popup](#markdown-header-add-custom-subscription-popup) is opened.
- Validate as you type: Not Empty.

#### Custom subscription popup subscription url input

- Label `Filter list URL`.
- When the text field is active or contains data, the label floats above the input area.
- Validates as you type against:
<!-- This is to technical, find a better way to describe it -->
```javascript
/^https?:/i
```

### Add custom subscription popup: Invalid
![](/res/abp/options-page/add-custom-subscription-popup-invalid.jpg)

If [Custom subscription popup subscription url input](#markdown-header-Custom-subscription-popup-subscription-url-input) is invalid show a small red *!*.

### Add custom subscription popup: Valid
![](/res/abp/options-page/add-custom-subscription-popup-valid.jpg)

If [Custom subscription popup subscription url input](#markdown-header-Custom-subscription-popup-subscription-url-input) is valid show a green *✓*.

#### Custom subscription popup cancel button

- Closes the [Add custom subscription popup](#markdown-header-add-custom-subscription-popup)
- Label `Cancel`

#### Custom subscription popup add button

- Adds filter list.
- Tab focus on the `Add filter list` button before `Cancel`.
- Inactive as long as [Custom subscription popup subscription title input](#markdown-header-custom-subscription-popup-subscription-title-input) and [Custom subscription popup subscription url input](#markdown-header-Custom-subscription-popup-subscription-url-input) don't validate.
- See [Advanced tab added filter list](#markdown-header-advanced-tab-added-filter-list)
- Label `Add filter list`

### Add custom subscription popup: Predefined

![](/res/abp/options-page/add-custom-subscription-popup-predefined.jpg)

- When a user adds a filter list by clicking on a subscribe-link from an external source, it should open the options page and display the above popup.
- Default dialog action is on the the primary button `Yes, add this filter list`
- Popup menu title:  `Are you sure you want to add this filter list?`
- Popup menu text:  
`Title: <Filter list title>` 
`URL: <Filter list URL>`
- If no filter list title is provided, only show the URL link. 	
	
| Button label | Behaviour |
|-----------|---------------|
| `Cancel` | Cancels action, and closes popup |
| `Yes, add this filter list` | Adds filter list to the table |

### Advanced tab: Added filter list

![](/res/abp/options-page/advanced-added-filter-list.jpg)

Newly added filter lists should be displayed at the top and marked with a dot.

#### Filter list table - empty state

![](/res/abp/options-page/advanced-filter-lists-empty.jpg)

- When alll filter lists have been removed from the extension. 
- Text: `You have not added any filter lists to Adblock Plus. Filter lists you add will be shown here.`
- [Update filter lists button](#markdown-header-update-filter-lists-button) is inactive.

#### Create custom filter section

![](/res/abp/options-page/advanced-default-custom-filter.jpg)

1. [Custom filter section header](#markdown-header-custom-filter-section-header)
1. [Custom filter section description](#markdown-header-custom-filter-section-description)
1. [Custom filter title](#markdown-header-custom-filter-title)
1. [Custom filter list placeholder](#markdown-header-custom-filter-list-placeholder)
1. [Create custom filter list button](#markdown-header-create-custom-filter-list-button)
1. [Create custom filter list link](#markdown-header-create-custom-filter-list-link)

#### Custom filter section header

`CREATE AND EDIT YOUR FILTER LIST`

#### Custom filter section description

`Write your own custom filters to further control what content Adblock PLus allows or blocks.`

#### Custom filter title 

`My filter list`

#### Custom filter list placeholder

`Filters you create will show up here.`

#### Create custom filter list button

- `Start writing my filter list`
- Opens [Advanced tab: Edit custom filter empty](#markdown-header-advanced-tab-edit-custom-filter-empty)

#### Create custom filter list link

`Learn how to write filter lists` opens the [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=filterdoc` in a new tab.

### Advanced tab: Custom filter empty

![](/res/abp/options-page/advanced-tab-custom-filter-empty.jpg)

#### Advanced tab: Custom filter start button

- `Start writing my filter list`
- Will open [Advanced tab: Edit custom filter empty](#markdown-header-advanced-tab-edit-custom-filter-empty)
- See also [Advanced tab: Custom filter hover](#markdown-header-advanced-tab-custom-filter-hover).

### Advanced tab: Custom filter hover

![](/res/abp/options-page/advanced-tab-custom-filter-hover.jpg)

[Advanced tab: Custom filter start button](#markdown-header-advanced-tab-custom-filter-start-button) will hover.

### Advanced tab: Edit custom filter empty

![](/res/abp/options-page/advanced-tab-edit-custom-filter-empty.jpg)
- Placeholder instruction text `e.g. /ads/track/*`

#### Advanced tab: Custom filter save button

- `Save`
- Will stay inactive as long as as no filter has been added.
- See also [Advanced tab: Edit custom filter add](#markdown-header-advanced-tab-edit-custom-filter-add)

#### Advanced tab: Custom filter cancel link

- `Cancel`
- Will revert all changes. If no custom filter switch to [Advanced tab: Custom filter empty](#markdown-header-advanced-tab-custom-filter-empty) otherwise show [Advanced tab: Custom filter](#markdown-header-advanced-tab-custom-filter).

### Advanced tab: Edit custom filter add

![](/res/abp/options-page/advanced-tab-edit-custom-filter-add.jpg)

### Advanced tab: Custom filter

![](/res/abp/options-page/advanced-tab-custom-filter.jpg)

#### Advanced tab: Enable/Disable custom filter list

![](/res/abp/options-page/advanced-tab-custom-filter-disabled.jpg)

- Checkbox to disable the custom filter list.
- Checkbox label: `Disable custom filter list`
- When the custom filter list is disabled, both the custom filter textinput section and the [Advanced tab: Custom filter edit button](#markdown-header-advanced-tab-custom-filter-edit-button) becomes inactive.

#### Advanced tab: Custom filter edit button

- `Edit filters`
- Will open [Advanced tab: Edit custom filter edit](#markdown-header-advanced-tab-edit-custom-filter-edit)

### Advanced tab: Edit custom filter edit

![](/res/abp/options-page/advanced-tab-edit-custom-filter-edit.jpg)

### Advanced tab: Invalid custom filter 

![](/res/abp/options-page/advanced-tab-edit-custom-filter-error-short.jpg)

- If a user enters an invalid filter, hightlight text input field in red.
- Notification reads: `Something's not right. Please check the following filters:`
- Filter strings which are invalid will populate as a list below the message.
- Show up to 5 invalid items in the list. If there are more than 5 invalid items display a bounding box and scroll bar as demonstrated in the image below.

![](/res/abp/options-page/advanced-tab-edit-custom-filter-error-long.jpg)

## Help tab

[Back to top of page](#markdown-header-options-page)

![](/res/abp/options-page/help-tab.jpg)

1. [Help tab headline](#markdown-header-help-tab-headline)
1. [Help tab description](#markdown-header-help-tab-description)
1. [Support section](#markdown-header-support-section)
1. [Get in touch section](#markdown-header-get-in-touch-section)

#### Help tab: Headline

- Headline for the [Help tab](#markdown-header-help-tab): `Help`
- Navigation label will match headline.

#### Help tab: Description

Description for the [Help tab](#markdown-header-help-tab): `Find help or get in touch with us`

#### Support section

- Title `Support`
- Bullet list (note: links are specific to language settings)
	- `Think content or functionality is being incorrectly blocked by us?`  `Report incorrectly blocked items here` (opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=adblock_plus_report_issue` in a new tab).
	- `See an ad that you think shouldn’t be there?` `Report an ad` (opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=adblock_plus_report_ad` in a new tab).
	- `Found a bug?`  `Send us a bug report` (opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=adblock_plus_report_bug` in a new tab)
	- `Want support from our community?`  `Go to the Forum`  (opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=reporter_other_link` in a new tab)

#### Get in touch section

- Title `Get in touch`
- Description `Have a question or a new idea? We're here to help.`
- Social media icons and links

| Social Media | Link URL | Browser locale |
|----------------|----------------| ----------------|
| `Twitter` | Opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=social_twitter` in a new tab | For all locales except *zh* |
| `Facebook` | Opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=social_facebook` in a new tab | For all locales except *zh* |
| `Google Plus` | Opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=social_gplus` in a new tab | For all locales except *zh* |
| `Weibo` | Opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link) `%LINK%=social_weibo` in a new tab | Only for the locales *zh* |

- `Email: support@adblockplus.org`

Assets
-------------

[Back to top of page](#markdown-header-options-page)

| Name | Asset | 
|-----------|---------------|
| ABP_Logo_Outline.svg | ![](/res/abp/options-page/assets/ABP_Logo_Outline.svg) |
| attention.svg | ![](/res/abp/options-page/assets/attention.svg) |
| box-circle.svg | ![](/res/abp/options-page/assets/box-circle.svg) |
| checkmark.svg | ![](/res/abp/options-page/assets/checkmark.svg) |
| code.svg | ![](/res/abp/options-page/assets/code.svg) |
| delete.svg | ![](/res/abp/options-page/assets/delete.svg) |
| email.svg | ![](/res/abp/options-page/assets/email.svg) |
| facebook.svg | ![](/res/abp/options-page/assets/facebook.svg) |
| globe.svg | ![](/res/abp/options-page/assets/globe.svg) |
| googleplus.svg | ![](/res/abp/options-page/assets/googleplus.svg) |
| reload.svg | ![](/res/abp/options-page/assets/reload.svg) |
| settings.svg | ![](/res/abp/options-page/assets/settings.svg) |
| tooltip.svg | ![](/res/abp/options-page/assets/tooltip.svg) |
| trash.svg | ![](/res/abp/options-page/assets/trash.svg) |
| twitter.svg | ![](/res/abp/options-page/assets/twitter.svg) |
