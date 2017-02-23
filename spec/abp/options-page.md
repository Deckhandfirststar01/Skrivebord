Options Page
============

Options page for the ABP Browser extension.

The options page is used to change various options of the ABP browser extension.

1. [Whitelist tab](#whitelist-tab)
1. [Advanced tab](#advanced-tab)

## General requirements

### Bidrirectionailty

Any change of state will be immidiatly reflected in the options page regardless
of where and how the change was made, so that the options page always reflects
the current state of the extension.

- If the user opens the option page more than once and makes changes to either
  of them, the change will be reflected in any of them and not just the one
  the change was made. 
- If a change to the state was made throught other means e.g. auto update of
  filter list subscriptions, it will be reflected immidiatly in every instance
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

***TODO***: Number don't match.

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

*NOTE: recently added has been ommitted because we don't now the date of when a domain has been whitelisted so we could only show the domains that have been added since the option page has been opened and that doesn't make any sense?!*

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

***TODO***: This is the default view, it has more than the default subscriptions

1. [Advanced tab headline](#advanced-tab-headline)
1. [Advanced tab description](#advanced-tab-description)
1. [Advanced tab: Custom filter empty](#advanced-tab-custom-filter-empty)


#### Advanced tab: Headline

Headline for the [Advanced tab](#advanced-tab): `Advanced`

#### Advanced tab: Description

Description for the [Advanced tab](#advanced-tab): `Customize your ad blocker, create your own filter lists`

#### Customize section headline

`CUSTOMIZE ON-PAGE ACTIONS`

#### Customize Block Element

Checkbox to en-/disable [Block Element Context Menu Entry](#TBA).

`Show 'Block Element’ right - click menu item`

***TODO***: Define tooltip

#### Customize Adblock Plus panel

Checkbox to en-/disable [Adblock Plus Developer Tools Panel](#TBA).

`Show 'Adblock Plus' panel in developer tools`

***TODO***: Define tooltip

#### Turn off notifications

Checkbox to en-/disable [Notifications](#TBA).

`Turn off notifications`

#### Filter list section headliner

`FILTER LISTS`

#### Filter list section description

```
Specify what content Adblock Plus allows or blocks by adding filters created
and maintained by our trusted community. [Learn more](#TBA)
```

#### List of filter list subscriptions

- ***XXX***: You can not see which subscriptions are enabled
- ***XXX***: You cannot see if the download was successful since the last 5 minutes

List headline: `Filter lists added`

Update column title: `Last updated`

List all filter list subsriptions. For each subscription show the following:

 - Name of the filter list
 - Date/Time of last update
   - Show `Just now` if less then 5 minutes ago
   - Show `{} minutes ago` if more than 5 minutes ago
   - Show `{} hours ago` if the last update was within the last 24 hours
   - Show `Updating` while the list is getting updated
   - Show `Download fail` when there is a problem downloading the filter list
 - A Gear Icon that opens the [Edit filter list popup](#edit-filter-list-popup)


#### Add filter list button

***XXX***: only adds one filter list at a time?!

Opens [Add filter list popup](#add-filter-list-popup).

`+ Add filter lists`

#### Update filter lists button

Updates all filters lists.

`Update all filter lists`

##### Add filter subscription popup

Allows to add a subscription.

#### Custom filter section headline

`CREATE / EDIT YOUR FILTER LIST`

#### Custom filter section description

`TBA`

#### Custom filter list title 

`My filter list`

#### Custom filter list placeholder


`Filters you create will show up here.`


-------------------------------------------------------------------------------

### Advanced tab: Added filter list

<img src='/res/abp/options-page/advanced-added-filter-list.jpg' width='888px' />

Newly added filter lists should be displayed at the top and marked with a dot.

-------------------------------------------------------------------------------

### Advanced tab: Custom filter empty

<img src='/res/abp/options-page/advanced-tab-custom-filter-empty.jpg' width='888px' />

***TODO***: Describe share functionality

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

Will revert all changes. If no custom filter switch to [Advanced tab: Custom filter empty](#advanced-tab-custom-filter-empty) otherwhise show [Advanced tab: Custom filter](#advanced-tab-custom-filter).

### Advanced tab: Edit custom filter add

<img src='/res/abp/options-page/advanced-tab-edit-custom-filter-add.jpg' width='888px' />

### Advanced tab: Custom filter

<img src='/res/abp/options-page/advanced-tab-custom-filter.jpg' width='888px' />

#### Advanced tab: Custom filter edit button

`Edit filters`

[Advanced tab: Custom filter edit button](#advanced-tab-custom-filter-edit-button) will hover.

Will open [Advanced tab: Edit custom filter edit](#advanced-tab-edit-custom-filter-edit)

***TODO***: Add hover layout

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

`Remove`


Add filter list popup
---------------------

Popup to add a filter list from a selection.

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/advanced-add-filter-list-popup.jpg' width='888px' />

***TODO***: Add aria requirements

### Add filter list popup title

`Add filter subscription`

### Close filter list popup X

Closes the [Add filter list popup](#add-filter-list-popup).

### List of available subscriptions

***TODO***: Add description of available subscriptions list.

### Add custom subscription link

Closes the [Add filter list popup](#add-filter-list-popup) and opens the [Add custom subscription popup](#add-custom-subscription-popup)

`+Add a filter list via URL`


Add custom subscription popup
-----------------------------

### Add custom subscription popup: Initial
<!-- XXX: don't use html -->
<img src='/res/abp/options-page/add-custom-subscription-popup.jpg' width='888px' />

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

Validates as you type:

***TODO***: Add actual validation criterias.


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

